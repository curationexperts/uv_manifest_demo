# Start a web server
```bash
ruby -rwebrick -e 'WEBrick::HTTPUtils::DefaultMimeTypes["json"]="application/json";WEBrick::HTTPServer.new(Port: 3002, DocumentRoot: Dir.pwd, RequestCallback: Proc.new{|req,res| res["Access-Control-Allow-Origin"] = "*" }).start'
```

# Change IIIF server in ENV
In the `env.development` file of your local Lux application, change your `IIIF_MANIFEST_URL` to `http://localhost:3002/concern/curate_generic_works/`

# Examples
* Boar Figurine - Metadata
  * https://digital-test.library.emory.edu/catalog/552w3r228t-cor
  * http://localhost:3001/catalog/552w3r228t-cor
* Civil War-era tourniquet - Download size
  * https://digital-test.library.emory.edu/catalog/822h70rxxb-cor
  * http://localhost:3001/catalog/822h70rxxb-cor
* Obstetric Instruments - Paged
  * https://digital-test.library.emory.edu/catalog/279v15dv4g-cor
  * http://localhost:3001/catalog/279v15dv4g-cor
