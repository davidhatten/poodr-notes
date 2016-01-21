* I lost a few lines of comments, I think mostly around how the distinction between private and public APIs doesn't exist in our domain
  * Thought about it some more, realized there's the ```abstract class``` pattern in java, but I almost always see that with a single ```execute()``` method
*  “Should Trip be responsible for figuring out if an appropriate bicycle is available for each suitable trip?” or more generally, “Should this receiver be responsible for responding to this message?”
  * I like this usage of sequence diagrams. Emphasizes as an exploratory/design tool rather than the official record of how things should be
  * Again there's an attempt to inject rubber duckies into the process, attempt to get the dev to think about their thought process
  * Software development is a never-ending process of examining your assumptions trying to make better ones. So much meta-analysis at the time of writing code
* "Instead of deciding on a class and then figuring out its responsibilities, you are now deciding on a message and figuring out where to send it."
  * Haven't heard this before, I think it makes the concept of message passing for more clear and easier to think about
* Good, we're finally diving into what "tell the objects what you want, not how to behave" actually means, because every book just seems to parrot that line without much elaboration
* This is probably because it's trivially simple, but I don't see a huge difference between Fig. 4.6 and Fig. 7.7
  *If aMechanic.prepare_bicycle took a list of bicycles instead of a single one, we'd be fine
  *aMechanic still needs to have a method that takes aTrip, and it needs to know that aTrip has bicycles. Before mechanic didn't need to know anything about Trip
  * I'm forseeing many objects that have a method ```prepare_trip(Trip)```
  * The Trip still needs the Mechanic object too
  * "Trip still knows that it holds onto an object that can respond to prepare_bicycle, and it must always have this object." Trip will always have to have an object that can respond to ```prepare_trip(Trip)``` too
  * So anything that has to interact with Trip like this needs to implement an interface and be handled as that type in the Trip class
  * So any class like that will be able to exactly one thing for Trip, as it will have to be handled via that type (in static languages)
  * "Expanding on this idea, Trip could place a number of such objects into an array and send each the prepare_trip message, trusting every preparer to do whatever it does because of the kind of thing that it is" precicely what I just said.
  * If none of those collaborators are expected to do anything else, that's fine. But reality is hardly that cut-and-dry
* A lot of this section feels influenced by the luxuries inherent in programming in a dynamically typed language
* I would like to see some of these more convoluted interface-based architectures implemented in Java. I've read about them plenty of times, but I've never seen one. At least not on a low enough level for me to have ever touched
* She is good at describing the feeling of when to do something, telling you about the heuristic
* <Sarcastic comment about trusting random developers not to do stupid things with your private methods>
* Wait a tic, I don't think she's used any form of the word "abstraction" in this chapter.
* But she just described how to abstract behavior into an interface. Well done
