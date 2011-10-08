!SLIDE bullets incremental

# \#input with :speak #

* Ask a question
* Allow the user to interrupt
* Interruption is taken as beginning of their answer

!SLIDE small

# \#input with :speak #

    @@@ ruby
    question = 'How many miles are on your car?'

    input :speak => {:text => question}

    # => 9999


!SLIDE bullets incremental

# \#input now accepts blocks #

* New way of signaling that input is satisfied
* Or determining that it's *unsatisfiable*
* Interactively validate input with each key-press

!SLIDE bullets incremental

# \#input with blocks #

## How it works ##

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
