# ShinyPromisesSnapshotLoader
Example of sequentially loading in intputs which create new sets of inputs which wouldn't exist without those inputs


## Motivation

This example is to demonstrate an issue with Shiny in practice. If you have a nested renderUI 
or even just a renderUI which generates a set of input which otherwise wouldn't exist, then
it is very easy to get into a situation whereby you can load in a bookmark, which then tries
to update a set of inputs which doesn't exist, triggering reactive chains which lead to errors
causing the whole app to fall over.  

This repo proves a minimal working example (MWE) of this issue, and also several
solutions, including:

- applying a hard-coded delay to the update of said inputs
- setting up asyncronous processing system to "wait" until the inputs exist before updating them

