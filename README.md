# Start a web server
In the directory where you have these examples, run a server on `localhost:3002`:
```bash
ruby -rwebrick -e 'WEBrick::HTTPUtils::DefaultMimeTypes["json"]="application/json";WEBrick::HTTPServer.new(Port: 3002, DocumentRoot: Dir.pwd, RequestCallback: Proc.new{|req,res| res["Access-Control-Allow-Origin"] = "*" }).start'
```

# Start your Application Server
I usually run my Curate application on `localhost:3000` and my Lux application on `localhost:3001`, so the links below are for a Lux application on `localhost:3001`.
* `bundle exec rails s -p 3001`

# Change IIIF server in ENV
In the `env.development` file of your local Lux application, change your
* `IIIF_MANIFEST_URL` to `http://localhost:3002/concern/curate_generic_works/`
* `SOLR_URL` to `http://solr-cor-test.library.emory.edu/solr/curate_collection`
* `THUMBNAIL_URL` to `https://curate-test.library.emory.edu/`

# Examples
* Boar Figurine - Metadata
  * https://digital-test.library.emory.edu/catalog/552w3r228t-cor
  * http://localhost:3001/catalog/552w3r228t-cor
* Civil War-era tourniquet - Download size
  * https://digital-test.library.emory.edu/catalog/822h70rxxb-cor
  * http://localhost:3001/catalog/822h70rxxb-cor
* Obstetric Instruments - Paged & Attribution
  * https://digital-test.library.emory.edu/catalog/279v15dv4g-cor
  * http://localhost:3001/catalog/279v15dv4g-cor
