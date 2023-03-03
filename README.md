
To reproduce, run SBT in a shallow clone of this repository:
```
git clone --depth 1 git@github.com:jackkoenig/dynver-check.git
cd dynver-check
sbt
```

You should see something like the following:
```
[info] welcome to sbt 1.8.2 (GraalVM Community Java 11.0.14)
[info] loading settings for project dynver-check-shallow-build from plugins.sbt ...
[info] loading project definition from /.../dynver-check-shallow/project
[info] compiling 1 Scala source to /.../dynver-check-shallow/project/target/scala-2.12/sbt-1.0/classes ...
[info] loading settings for project root from build.sbt ...
[error] Failed to derive version from git tags. Maybe run `git fetch --unshallow`? Version: 0.0.0+1-a30a44e9
[warn] Project loading failed: (r)etry, (q)uit, (l)ast, or (i)gnore? (default: r)
```

You can indeed resolve the issue with `git fetch --unshallow`, but the idea is that the error would only show up when you actually run `sbt doc` or some dependent Task.
