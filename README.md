**This is a PMMP-only mailer. The https://github.com/PHPMailer/PHPMailer source code was taken from and made for PMMP.**

---

## Example

```php
use gamegam\PHPMailer\PHPLoader;

$mail = PHPLoader::getInstance();
$host ='smtp.google.com';
$useremail ="your email";
$password = "your password";
$port = 587;
$ssl = "SSL";
$body = "Email Content</br>This is the email delivery. \nUse </br> instead";

try {
    $mail->isSMTP();
    $mail->SMTPDebug = 0;
    $mail->CharSet = 'UTF-8';
    $mail->Host = $host;
    $mail->SMTPAuth = true;
    $mail->Username = $useremail;
    $mail->Password = $password;
    $mail->SMTPSecure = $ssl;
    $mail->Port = $port;

    $mail->addAddress($email, "username");
    $mail->setFrom($useremail, 'gamegam');

    $mail->isHTML(true);
    $mail->Subject = $title;
    $mail->Body = $body;

    $mail->Timeout = 1;
    $mail->send();

    echo "email send";
} catch (\Exception $e) {
    echo $e->getMessage();
}
