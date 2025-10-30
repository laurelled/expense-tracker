## Learn More

To learn Fastify, check out the [Fastify documentation](https://fastify.dev/docs/latest/).

## Other paragraph worth adding to the README.md
Consider the process of writing the Readme for your project as the true act of creation.
Take some time at the start of the project to write the README, as it's one of the best descriptions of what the project will look like. From Tom Preston's article called [README Driven Development](https://tom.preston-werner.com/2010/08/23/readme-driven-development.html): 
> "_You’ll also find that it’s much easier to write this document at the beginning of the project when your excitement and motivation are at their highest_"

> "_It’s a lot simpler to have a discussion based on something written down. It’s easy to talk endlessly and in circles about a problem if nothing is ever put to text._"

* What are the project’s requirements? Do you need a database or some other external resources?
* How do you install the application? What package manager and Node.js version does it use?
* How do you start the application? Where can missing data (such as environment variables)
be found?
* How do you develop the application? Are there some conventions that developers must follow?
* How do you test the application? Does it require unit tests or end-to-end tests?
* How do you deploy the application? What are the processes and the environment’s URLs?
* What should a developer do if there is missing information?

## Testing

Tests should be included in the `/test` folder. Test implementation depends on the project implementation. Only after we have reached a stable solution will we be able to write our basic assertions, such as the following:
• The application starts correctly
• The configurations are loaded in the right order