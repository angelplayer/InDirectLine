
## A Big picture

```
   +--------------------+                 +----------+
   |                    <-------------+   |          |
+--|    Service  Url    |--+          |   |          |
|  |                    |  |          |   |          |
|  +--------------------+  |          |   |          |
|                          |          |   |Bot Server|
|    DirectLine   Bridge   |          |   |          |
|                          |   +------+---+--+       |
|  +--------------------+  |   |Message API  |       |
|  |                    |  |   +------^---+--+       |
+--|DirectLine Endpoints|--+          |   |          |
   |                    +-------------+   |          |
   +--------^---+-------+                 +----------+
            |   |
            |   |
            |   |
+-----------+---v------------------------------------+
|                                                    |
|               DirectLine Clients                   |
|       (e.g. WebChat/ DirectLinetClient/...)        |
|                                                    |
+----------------------------------------------------+
```

## A Detailed View

```
                     +------------------+                +-------+
                     |                  |                |       |
                     |   Conversation   <----------------+       |
                     |    Controller    |                |       |
                     |                  +---------------->       |
                     +------------------+                |       |
                                                         |       |
+---------+          +------------------+                |       |
|         +---------->                  |                |       |
|         |  token   | Token Controller |                |       |
|         <----------+                  |                |Adaptor|
|         |          +------------------+                |       |
|         |                                              |       |
| Client  |          +------------------+                |       |
|         +---------->                  +---------------->       |
|         |          |    DirectLine    |                |       |
|         | Activity |                  <----------------+       |
|         |          |    Controller    |                |       |
|         <----------+                  |                |       |
+---------+          +------------------+                +-------+
```