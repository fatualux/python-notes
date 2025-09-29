# Dependency Inversion Principle

”The Dependency Inversion Principle (DIP) tells us that the most flexible 
systems are those in which source code dependencies refer only to 
abstractions, not to concretions.” 
(Robert C. Martin, Clean Architecture)

”a. High-level modules should not depend on low-level modules. Both 
should depend on abstractions.
b. Abstractions should not depend on details. Details should depend on 
abstractions.” 
(Robert C. Martin, Agile Software Development)

## CONCLUSION

Prefer to depend on abstractions (i.e. abstract classes or 
concepts) instead of concrete types.

### PRACTICAL EXAMPLE

Wrong way:

```python
class EmailService:
    def send_email(self, to: str, message: str, receiver: str) -> None:
        print(f"Sending email: {message} to {receiver}")

class SmsSwervice:
    def send_sms(self, to: str, message: str, receiver: str) -> None:
        print(f"Sending SMS: {message} to {receiver}")

class NotificationService:
    def __init__(self) -> None:
        self.email_service = EmailService()
        self.sms_service = SmsSwervice()

    def send_notification(
        self, to: str,
        message: str,
        receiver: str,
        method: str
        ) -> None:
        if method == "email":
            self.email_service.send_email(to, message, receiver)
        elif method == "sms":
            self.sms_service.send_sms(to, message, receiver)
```

In this code, the NotificationService class directly depends on the concrete
classes EmailService and SmsService.
This violates the DIP, which states that high-level modules should not depend
on low-level modules;both should depend on abstractions.

The direct dependency on concrete classes makes the NotificationService
less flexible and harder to change or extend, as it's tightly coupled to
specific implementations of the email and SMS services.


Right way:
```python
class MessageService:
    def send(self, to: str, message: str, receiver: str) -> None:
        pass


class EmailService(MessageService):
    def send(self, to: str, message: str, receiver: str) -> None:
        print(f"Sending email: {message} to {receiver}")

class SmsService(MessageService):
    def send(self, to: str, message: str, receiver: str) -> None:
        print(f"Sending SMS: {message} to {receiver}")

class NotificationService:
    def __init__(self, message_service: MessageService) -> None:
        self.message_service = message_service

    def send_notification(
        self, to: str,
        message: str,
        receiver: str
        ) -> None:
        self.message_service.send(to, message, receiver)
```

In the refactored solution, we introduce an abstract class with an
IMessageService abstract method send().
Both EmailService and SmsService now implement
the IMessageService interface.
The NotificationService class now depends on the abstraction IMessageService
rather than the concrete classes Email Service and SmsService.
This adheres to the DIP because both high-level and low-level classes depend
on abstractions rather than concrete implementations, making the code more
flexible and easier to change or extend.