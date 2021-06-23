# craftsmanship

## Intro
I was in sketchers shoe store the other day, waiting to try several shoes when it hit me that giffgaff has no formal guidelines on craftsmanship. Perhaps this is a good thing, because as soon as formal guidelines are written, then the fun drops away. 

Craftsmanship is different things to different people. Like art. Like a swiss watch. Like a scuplture. Certain things will be appreciated over others. As such it's not easy to define, but when you see it, you know it.

Software as always, borrows from other industries to get concepts articulated. Craftsmanship with respect to software is yet another borrow. Conversely, we all know what crappy code looks like. So I decided, while waiting between shoes, to jot down a list of things, taken from my 20 years experience, that I'd personally regard as craftmanship. As such, feel free to take what you like from this list. It's mine. It's subject to change. They are things I keep in my head while coding. So I thought I'd share with you instead of keeping in my head.


Wills Craftsmanship List


1. Keep it simple. Simple is pure.
2. Code for today - not if/maybe in the future
3. Code is closed for modification open for inspection
4. Classes have a single responsiblity (SRP)
5. Use Lombok judiciosly
6. Generally favour aggregation over inheritance
7. Pojos : Use Lombok builders judiciously with final public fields
8. Avoid complex persistence (ie relational dbs). No one cares about your mappings.
9. Use java uuids
10. Controllers should have only one delegate domain class. Controllers exist for validation before transforming into business objects.
11. Solve the business problem first using an interface layer for persistence and an interface/facade layer for inputs. Once done the rest of the soln will drop out.
12. Ask yourself questions all the time: what’s this classes's job in life...who’s calling this method and why. Could things be better/simpler by moving a field to another class, can I reduce the scope?
13. Build your spring in a config class where possible. It simplifies the magic going on underneath and allows you to see how assembly ought to be. It also keeps Java class pure. (Free of spring).
14. Hexagonal architecture is good
15. Use the tell don’t ask principle. If you’re poking a class for info twice - it’s a code smell.
16. Use clean code principles. Know them.

For an example of these see the https://github.com/giffgaff/reference-data-library repo

### Thoughts on tests

1. Require a different hat/mindset to coding.
2. Make use of package scope for testability of methods that require it
3. Use test fixtures
4. Prefer single unit tests over parameterised. Don’t test everything. Tests provide intent, documentation. Tests must be dead easy to read and simpler than source.
5. Always Use hard coded constants in tests.
6. Have at least one spring integration test to capture key issues early.
7. Don’t write tests first unless you don’t know how to build the domain model. It’s an expensive way to develop due to refactoring overhead on tests.
8. System tests are good

### A bit on the repo, readme and other stuff

1. Readme should be one page long, have an architecture diagram a description of business intent/ reason for existence. Link for developers
1. The dev link must have links for prod/stage/dev
1. Each of those environments must describe build and pipeline deploy, kibana logs, k9s, graphana metrics. Why? so everyone knows how the code gets into prod.
1. Your repo readme is your shop window. Do it well and it sells your code like honey to bees. NEVER underestimate its power. No readme = no interest. Why should another dev want to work on your code? When you consider two competing repos on github, which one wins and why?
1. Use pairing intelligently. Be willing to engage argue and learn. Respect your elders, they've been around.
1. Do your own PR and review it before assigning others. You’ll always find something.
2. Keep you build time short. A good project can die if the build time is too long. (10 mins)
3. When reviewing others, give a little slack. No one likes an ass.


