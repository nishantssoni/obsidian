To see the data flowing into Redis, you need to open a **second terminal window** (leave your Python simulator running in the first one) and jump inside the Redis database.

Here are the exact commands to prove your pipeline is working, going from a simple check to a full "Matrix-style" live feed.

### Step 1: Open the Redis CLI

In your new terminal window, run this command to drop directly into the database command line:

Bash

```
docker exec -it my-redis-test redis-cli
```

_(Your prompt should change to something like `127.0.0.1:6379>`)_

### Step 2: The Quick Check (Is it growing?)

To see how many total GPS packets are currently sitting in your queue, use the `XLEN` (Stream Length) command:

Plaintext

```
XLEN fleet_telemetry_stream
```

Run this command a few times in a row. Because your script pushes 100 packets every second, **you should see this number jump by exactly 100 every time you press Enter.**

### Step 3: Inspect the Newest Data Packet

To actually look at the JSON data inside the stream, we want to pull the absolute newest record. Use the `XREVRANGE` (Reverse Range) command to grab the top 1 item:

Plaintext

```
XREVRANGE fleet_telemetry_stream + - COUNT 1
```

You will see output that looks like this:

Plaintext

```
1) 1) "1717540000000-0"  <-- The unique Redis Timestamp ID
   2) 1) "data"
      2) "{\"truck_id\": \"TRUCK_042\", \"lat\": 23.3512, \"lng\": 85.3211, \"speed_mph\": 45, \"cargo\": \"Electronics\", \"timestamp\": 1717540000}"
```

_This proves your JSON is perfectly formatted and ready for PostGIS!_

### Step 4: "The Matrix Mode" (Live Tailing)

If you want to sit back and watch the data fly in real-time, just like a server log, you can tell Redis to `BLOCK` (wait) and print every new message the millisecond it arrives (`$` means "only show me new stuff from this moment forward"):

Plaintext

```
XREAD BLOCK 0 STREAMS fleet_telemetry_stream $
```

Your screen will instantly start scrolling endlessly with the 100-packet-per-second stream!

_(To stop the live matrix scrolling, just press `Ctrl + C` to exit the Redis CLI)._

Once you confirm the data is flowing and you see those coordinates dropping into Redis, you have officially built a high-throughput message broker! Let me know when you see the data, and we will write the `docker-compose.yml` to spin up our massive **PostGIS** spatial database!