!SLIDE bullets incremental

# :speak and \#input #

* Ask a question
* Allow the user to interrupt and answer


!SLIDE small

    @@@ ruby
    question = 'How many miles are on your car?'

    input :speak => {:text => question}

    # => 9999


!SLIDE bullets incremental

# \#input now accepts blocks #

* New way of signaling that input is satisfied
* Or immediately validating input

!SLIDE bullets incremental

# How it works #

* Your block evaluated after every key-press
* Return `true` inside your block to stop


!SLIDE bullets incremental

# Example #

* Ask the user for a phone number
* Require a (415) or (510) area code
* Stop early if their number isn't matching up

!SLIDE small

# A local phone number #

    @@@ ruby
    
    input 10 do |number|

      # Could the number begin with 415 or 510?
      is_local = number =~ /^41?5?|^51?0?/

      # If it isn't local, stop collecting input
      ! is_local

    end
