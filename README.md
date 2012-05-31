# feedback_popup

为Rails3准备的简单的feedback系统， 修改于https://github.com/peerpost/feedback_popup
主要做了一些中文上的修改和更改了颜色，自己不喜欢太明显的颜色。

## Installation

Add to your `Gemfile`:

```ruby
gem 'feedback_popup',:git => "git://github.com/chucai/feedback_popup.git"
```

Run `bundle install`

`config/initializers/feedback_popup.rb`:

```ruby
FeedbackPopup.setup do |config|
  config.mail_to   = 'you@example.com'
  config.mail_from = 'sender@example.com'
end
```

Add to your `app/assets/stylesheets/application.css' or equivalent,
normally just before the `require_tree` line:

```
 *= require feedback_popup
```

Add to your `app/assets/javascripts/application.js' or equivalent,
normally just before the `require_tree` line:

```
//= require feedback_popup
```

Add to your layout:

```
<%= feedback_popup %>
```

Make sure you have ActionMailer configured.

Restart your app.

关于Gmail的设置
Add to your `app/config/application.rb`
```
    ActionMailer::Base.smtp_settings = {
      :address        => 'smtp.gmail.com',
      :port           => '587',
      :domain         => 'gmail.com',
      :authentication => :plain,
      :user_name      => ENV['GMAIL_USERNAME'],
      :password       => ENV['GMAIL_PASSWORD'],
      :enable_starttls_auto => true
    }
    ActionMailer::Base.delivery_method = :smtp
    config.action_mailer.raise_delivery_errors = true
```

## Copyright

See the MIT-LICENSE file.
