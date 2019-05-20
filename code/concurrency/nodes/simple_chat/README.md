# SimpleChat

**Basic chat app demonstrating processes and distribution features of Elixir (Erlang)**

## Usage

  1. Server
        ```
        iex --sname server -S mix
        iex(server@yourcomputername)1> SimpleChat.Server.start
        ```

  2. Client(s) - each client functioning in different terminal sessions
        ```
        iex --sname client1 -S mix
        client1> SimpleChat.Client.join_server :"server@yourcomputername"
        
        iex --sname client2 -S mix
        client2> SimpleChat.Client.join_server :"server@yourcomputername"
        
        iex --sname client3 -S mix
        client3> SimpleChat.Client.join_server :"server@yourcomputername"
        
        client1> SimpleChat.Client.broadcast "sup sup"
        client2> client1: sup sup
        client3> client1: sup sup
        
        client1> SimpleChat.Client.friends
        client1> [:"client2@yourcomputername", :"client3@yourcomputername"]
        
        client1> SimpleChat.Client.direct_message :"client3@yourcomputername", "hey there, you!"
        client3> client1: hey there, you!

        ```
