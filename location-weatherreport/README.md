### Overview
For a full tutorial on importing schemas into your StepZen project, the main [Readme](https://github.com/steprz/stepzen-schemas) of this repository provides step-by-step instructions to do so.

## StepZen Import <a href="import"></a>
<em>The location-weatherreport is an [directive schema](https://my.stepzen.com/docs/reference/code/#set-of-directives) that uses the @materializer directive to stitch your data together.  Read more about how StepZen directives can unify your data here, https://my.stepzen.com/docs/reference/code/#set-of-directives</em>

1. Before importing the schema, either create a new project or access your existing project in the command line.

Creating a new StepZen SDL project.
```bash
$ mkdir my-app
$ cd my-app
```

Access an existing project
```bash
$ cd my-existing-project
```

2. Importing the schema. Be sure to import location and weatherreport templates to use this directive schema properly.

```bash
$ stepzen import location weatherreport location-weatherreport
```

3. Now the project should include the following directory layout in your root folder.

```shell
🐒➔ tree
.
├── index.graphql
├── config.yaml
└── location-weatherreport
    ├── Location-Weatherreport.graphql
    └── README.md

1 directories, 4 files
```

4. Start up the StepZen Endpoint. Provide the directory path to deploy your endpoint appropriately.  
<em>https://accountname.stepzen.net/foo/bar/__graphql</em>


```bash
$ stepzen start foo/bar
```
A successfull deploy should respond with the below CLI message. If it did not successfully deploy, post on [Github Issues](https://github.com/steprz/stepzen-schemas/issues)
```bash
Watching /Users/username/Desktop/myapp/config.yaml for configuration changes
Watching /Users/username/Desktop/myapp for GraphQL changes

http://localhost:5000/foo/bar
Deploying to StepZen...... done

Successfully deployed foo/bar at 8:06:59 AM

Your endpoint is available at https://accountname.stepzen.net/foo/bar/__graphql
```

Done! The StepZen Dashboard should be deployed at `http://localhost:5000/foo/bar` with an explorer listing the query documentation. 🚀

![Localhost](https://res.cloudinary.com/dvfhnc6ui/image/upload/v1614608265/stepzen-localhost-dashboard.png)

## 

Not signed up for StepZen? Try it free here -> https://stepzen.com/request-invite