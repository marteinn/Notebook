# Job processing libraries in Elixir/Erlang

## When should you use GenServer?
- No persistance requirement

## When should you use a queue handler?
- When you need to persist your queue (GenServer lose their state when they die)
- Consistency between nodes


## Libraries

- exq (724)
https://github.com/akira/exq
Exq is a job processing library compatible with Resque / Sidekiq for the Elixir language.
Includes a ui in the form of [exq_ui](https://github.com/akira/exq_ui)

- verk (397)
https://github.com/edgurgel/verk
Verk is a job processing system backed by Redis.

- Toniq (251)
https://github.com/joakimk/toniq
Simple and reliable background job processing library for Elixir.

- que (254)
https://github.com/sheharyarn/que
Simple Job Processing in Elixir with Mnesia


## Articles

- [Background Jobs in Elixir & Phoenix](https://medium.com/@cschneid/background-jobs-in-elixir-phoenix-60dddf4ce207)
- [Exq: The background job solution for Phoenix](http://learningwithjb.com/posts/exq-the-background-job-solution-for-phoenix)
- [Elixir Job Processing with Exq](https://elixircasts.io/elixir-job-processing-with-exq)
- [Background processing using Elixir, GenServer and the Erlang queue module
](https://hackernoon.com/background-processing-using-elixir-genserver-and-the-erlang-queue-class-8d476d4942c2)
- [A nice guide with genserver video tutorials](https://www.youtube.com/channel/UCp01DFl8kp-239gW289C0ew)
- [Need an Elixir dependency to manage recurring jobs? Not so fast!](https://dockyard.com/blog/2017/11/29/need-an-elixir-dependency-to-manage-recurring-jobs-not-so-fast)
