# Web App Explorations

This is an exploration of web app built on node. Eventually this will run on a Raspberry Pi that is retreiving data from 
the PIO pins and $I^2C$ devices.  This may include output as well as input.

General things I need to learn:
  - How async operations work with the Promise model of code handling
    - looks like any function declared with an 'async' prefix automatically becomes a promise object.
    - Promise objects need to be provided functions (or lambda functions) that complete the transaction or respond to various options of what the promise can transfer.
  - When do I control caching and update content pushed from the server vs being requested by client?
    - If the data is static then cache. If it is fluid then get it on the fly.  The interesting thing with the experiments is that if the returned data isn't querried or operated on it loads more slowly. (or appears to)

## Naive starting point: Quotes
I have a server file which contains quotes in a text file. I read the file in to a server script and serves pages with a randomly changing choice from the file.  
  - Currently this is driven by the client updating the page using a refresh. **Is there a way the server can push this out?**  
  - I write all the structural elements directly within the code. **Is this the best way to do this or should the static bits be in a file with the program managing the dynamic elements?**
    - Jury's still out on this one. Getting information back and forth might be a bit tricky but I am now looking at wrtiting code that does requests through fetch calls.  Push tech is still above my paygrade right now.  I am still thinking a simple socket layer would be OK.
    - [Methods for transferring data](https://www.c-sharpcorner.com/UploadFile/suthish_nair/different-ways-to-pass-data-between-web-forms/) gives a nice summary of options.
