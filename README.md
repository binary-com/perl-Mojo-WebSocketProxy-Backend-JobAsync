# NAME

Mojo::WebSocketProxy::Backend::JobAsync

# DESCRIPTION

A subclass of [Mojo::WebSocketProxy::Backend](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3ABackend) which dispatches RPC requests
via [Job::Async](https://metacpan.org/pod/Job%3A%3AAsync).

# CONSTANTS

## QUEUE\_TIMEOUT

A duration of timeout in seconds (default: 300) for receiving response from RPC queue.
The default value can be orverriden by setting an environment variable of the same name:

    $ENV{QUEUE_TIMEOUT} = 2;

# CLASS METHODS

## new

Returns a new instance. Required params:

- loop => IO::Async::Loop

    Containing [IO::Async::Loop](https://metacpan.org/pod/IO%3A%3AAsync%3A%3ALoop) instance.

- jobman => Job::Async

    Optional [Job::Async](https://metacpan.org/pod/Job%3A%3AAsync) instance. If non-empty, it should be already added to the `loop`.

- client => Job::Async::Client

    Optional [Job::Async::Client](https://metacpan.org/pod/Job%3A%3AAsync%3A%3AClient) instance. If non-empty, it should be constructed by  `$jobman->client`.
    Will be constructed from `$jobman->client` if not provided.

# METHODS

## client

    $client = $backend->client

Returns the [Job::Async::Client](https://metacpan.org/pod/Job%3A%3AAsync%3A%3AClient) instance.

## loop

    $client = $backend->loop

Returns the async IO loop object.

## jobman

    $jobman = $backend->jobman

Returns an object of [Job::Async](https://metacpan.org/pod/Job%3A%3AAsync) that acts as job manager for the queue client.

## call\_rpc

Implements the ["call\_rpc" in Mojo::WebSocketProxy::Backend](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3ABackend#call_rpc) interface.

# SEE ALSO

[Mojolicious::Plugin::WebSocketProxy](https://metacpan.org/pod/Mojolicious%3A%3APlugin%3A%3AWebSocketProxy),
[Mojo::WebSocketProxy](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy)
[Mojo::WebSocketProxy::Backend](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3ABackend),
[Mojo::WebSocketProxy::Dispatcher](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3ADispatcher),
[Mojo::WebSocketProxy::Config](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3AConfig)
[Mojo::WebSocketProxy::Parser](https://metacpan.org/pod/Mojo%3A%3AWebSocketProxy%3A%3AParser)

# COPYRIGHT AND LICENSE

Copyright (C) 2022 Deriv Group Services Ltd
