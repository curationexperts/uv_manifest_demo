# Start a web server
```bash
ruby -rwebrick -e 'WEBrick::HTTPUtils::DefaultMimeTypes["json"]="application/json";WEBrick::HTTPServer.new(Port: 3002, DocumentRoot: Dir.pwd, RequestCallback: Proc.new{|req,res| res["Access-Control-Allow-Origin"] = "*" }).start'
```

# Change IIIF server in ENV
In the `env.development` file of your local Lux application, change your `IIIF_MANIFEST_URL` to `http://localhost:3002/`
