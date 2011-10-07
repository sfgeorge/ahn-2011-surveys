!SLIDE bullets incremental

# It can talk #

* New #speak command
* Supports Tropo, Cepstral, and UniMRCP
* Speaking TTS has never been easier

!SLIDE

# \# speak #

    @@@ ruby
    speak "Hello, welcome to Joe's"

# Allow the user to interrupt #

    @@@ ruby
    speak 'Let me tell you a long story...',
      :interruptible => true

!SLIDE

# \# speak is easy to config #

Specify your preferred speech engine in `config/startup.rb`

    @@@ ruby
    config.asterisk.speech_engine = :tropo

!SLIDE

# \# speak is easy to config #

Or change it up at run-time

    @@@ ruby
    speak 'How can we help you today?',
      :engine => :unimrcp


    speak 'How can we help you today?',
      :engine => :cepstral

<!-- @todo:
* talk about ssml
* ruby_speech - mention the github url
-->

