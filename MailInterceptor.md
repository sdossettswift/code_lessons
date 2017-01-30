# Mail Interceptor
##Goals
Make sure emails are setup correctly, while eliminating the possibility of
sending test emails that should not be sent!

### Step One: /lib/development_mail_interceptor.rb

```class DevelopementMailInterceptor
  def self.delivering_email(message)
    message.subject = "#{message.to} #{message.subject}"
    message.to = 'your email address"
    message.bcc = ""
    message.cc = ""
  end
end
```
