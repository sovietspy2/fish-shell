continue - skip the remainder of the current iteration of the current inner loop
================================================================================

Synopsis
--------

LOOP_CONSTRUCT; [COMMANDS...;] continue; [COMMANDS...;] end


Description
-----------

``continue`` skips the remainder of the current iteration of the current inner loop, such as a <a href="#for">for</a> loop or a <a href="#while">while</a> loop. It is usually added inside of a conditional block such as an <a href="#if">if</a> statement or a <a href="#switch">switch</a> statement.

Example
-------

The following code removes all tmp files that do not contain the word smurf.



::

    for i in *.tmp
        if grep smurf $i
            continue
        end
        # This "rm" is skipped over if "continue" is executed.
        rm $i
        # As is this "echo"
        echo $i
    end

