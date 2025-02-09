# Summarize

Wack Hacker has the ability to summarize conversations in a channel
using the `/summarize` command. This command will generate a summary of
the last hour of messages in the channel and create a thread containing
the summary.

It will attempt to track the flow of the conversation and then summarize
any outcomes that were formed from the conversation.

- `/summarize <topic> <optional:timeframe>`: Generates a summary of messages
  from x timeframe (default: past 1 hr) in the channel and creates a thread
  containing the summary.
