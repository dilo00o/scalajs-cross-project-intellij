# Scala.js Cross Project working with IntelliJ

The only important part in this repository to make IntelliJ happy, is to declare the shared project with its libraryDependencies in your [sbt build file](https://github.com/vmunier/scalajs-cross-project-intellij/blob/8c004a5e487d30eecb4c1276fd04ae3c7167ae9e/build.sbt#L13-L15). You don't need to use symbolic links.

## Try it Yourself

1. `$ sbt gen-idea`
2. Inside IntelliJ, `File/Open...`, choose the root folder to import all the projects (do *not* use `Import Project...` or `Import Module...`)

## IntelliJ 14

You will be prompted to convert the old format to a new format. Just click `Convert`.

## Changes in build.sbt

Here's the annoying part. Every time you do some changes in build.sbt, import a fresh new IDEA project:
```
Inside IntelliJ, delete scalajs-cross-project-intellij, then
$ cd scalajs-cross-project-intellij
$ rm -r .idea/ .idea_modules/
$ sbt gen-idea
Inside IntelliJ, File/Open..., choose scalajs-cross-project-intellij to import all the projects
```

## Run the application

Run the jvm project from sbt:
```
$ sbt
> exampleJVM/run
```
Run the js project from sbt:
```
$ sbt
> exampleJS/run
```
Run the javascript output file in a web browser:
```
$ sbt
> exampleJS/fastOptJS
$ open index-fastopt.html
```
