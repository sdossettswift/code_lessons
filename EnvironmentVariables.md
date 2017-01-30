#Environment Variables
## goals:
connect to external APIs, use version control, and keep API keys
protected

### .env File

`export AWS_ACCESS_KEY_ID="**********************
export AWS_SECRET_ACCESS_KEY="**********************"
export AWS_S3_BUCKET="************"
export LINKEDIN_CONSUMER_KEY="***********"
export LINKEDIN_CONSUMER_SECRET="***********"
export MAILCHIMP_API_KEY="***********"
export MAILCHIMP_LIST_ID="*******"
export MAILCHIMP_COVERAGE_GROUP_ID="*******"
export MAILCHIMP_ALE_STATUS_GROUP_ID="*******"
export MAILCHIMP_COVERAGE_BUCKET_ID="*******"`


### Add .env file to .gitignore

`.env`


### environment.rb File

`<!-- # Load the Rails application. -->
require File.expand_path('../application', __FILE__)

<!-- # Initialize the Rails application. -->
AppName::Application.initialize!
ENV['AWS_ACCESS_KEY_ID']
ENV['AWS_SECRET_ACCESS_KEY']
ENV['LINKEDIN_CONSUMER_KEY']
ENV['LINKEDIN_CONSUMER_SECRET']
ENV['MAILCHIMP_API_KEY']
ENV['MAILCHIMP_LIST_ID']
ENV['MAILCHIMP_COVERAGE_GROUP_ID']
ENV['MAILCHIMP_COVERAGE_BUCKET_ID']
ENV['MAILCHIMP_ALE_STATUS_GROUP_ID']
`
