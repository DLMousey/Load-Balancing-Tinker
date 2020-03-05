# Load Balancing Tinker (lb-tinker)

Nothing particularly exciting going on in here, just fiddling around with load balancing using HAProxy. This repo is pretty much identical to DLMousey/Microservices-Tinker.

## Setting up

If you'd like to fiddle around with this yourself;

- Modify `/etc/hosts`, add the following new lines to the end of the file;
```
127.0.0.1 lbhost
```

- Clone this repo

- Run `make dev` or `docker-compose up --build` if you don't have `make` installed. You will see a _lot_ of output.
Eventually you will see `host1`, `host2` and `host2` report that they are running - the applications have now started.

- Navigate to the following URL in your browser;
```
http://lbhost/api/ping
```

You should see a response following this format;
```json
{ 
  "status":200,
  "message":"Pong from host [HOST-NUMBER]"
}
```

- To stop the server just hit `ctrl + c`
- To start the servers again in `detached` mode, run `make headless`
- To stop the servers again while in `detached` mode, run `make stop`
