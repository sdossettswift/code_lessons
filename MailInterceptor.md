# Mail Interceptor
##Goals
Make sure emails are setup correctly, while eliminating the possibility of
sending test emails that should not be sent!

### Step One: /lib/development_mail_interceptor.rb

```ruby
class DevelopementMailInterceptor
  def self.delivering_email(message)
    message.subject = "#{message.to} #{message.subject}"
    message.to = "your email address"
    message.bcc = " "
    message.cc = " "
  end
end
```


### Step Two: config/initializers/setup_mailer.rb

```ruby
require 'development_mail_interceptor'

ActionMailer::Base.register_interceptor( DevelopmentMailInterceptor) unless
Rails.env.production?
```


### What's Going On
In Step One, you sub your email address for the 'message.to'. To make sure the
email doesn't get sent to any BCC or CC recipients, change both variables to
''. Then, in order to be able to trace your test emails to the events that
triggered, move the original recipient's email address into the subject line. 

To put step one to action, you have to loop the file in during initialization.
So, first you require the 'development_mail_interceptor' file. That brings the
file in. Then, you use the DMI unless you are in production mode. All emails
sent in test, dev, or staging will be intercepted. In production, nothing is
changed. 
