!SLIDE bullets incremental

# It can talk! #

* Ability to *dynamically* say anything
* Extremely powerful


!SLIDE bullets incremental

# New \#speak command #

* Supports Tropo, Cepstral, and UniMRCP
* Speaking TTS has never been easier


!SLIDE bullets incremental

# Easy to config #

In `config/startup.rb`:
    @@@ ruby
    config.asterisk.speech_engine = :tropo

* Also supports `:cepstral` and `:unimcrp`


!SLIDE

# And then... Voila #

<br />

    @@@ ruby
    speak "Hello, welcome to Joe's"
    

!SLIDE

    @@@ ruby
    speak "Your #{vehicle} will be ready in"
      << " #{time_remaining} hours"


!SLIDE

## Allowing the user to interrupt us ##

    @@@ ruby
    speak 'Let me tell you a long story...',
      :interruptible => true


!SLIDE bullets incremental

# SSML works too #

* Speech Synthesis Markup Language
* Speech properties such as pitch, rate and gender


!SLIDE bullets incremental

# New ruby_speech gem #

github.com/benlangfeld/ruby_speech

* Create rich SSML w/o touching markup!
* Because DSL &gt; markup

!SLIDE smaller

# So instead of this... #

    @@@ ruby
    statement = '<?xml version="1.0"?>
      <speak
        xmlns="http://www.w3.org/2001/10/synthesis"
        version="1.0"
        xml:lang="en-US">
        <voice gender="male">
          Your bill is due on
          <say-as interpret-as="date" format="mdy">
            10/15/2011
          </say-as>
        </voice>
      </speak>'

    speak statement

!SLIDE smaller

# ...You can do this: #

    @@@ ruby
    speak RubySpeech::SSML.draw do
      voice gender: :male do
        string 'Your bill is due on'
        say_as interpret_as: 'date', format: 'mdy' do
          '10/15/2011'
        end
      end
    end


