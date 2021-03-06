## Gogradle 0.11 release note

We're glad to release Gogradle 0.11.

### Improvements in Gogradle 0.11

- Gradle 5.x support.
- JDK 11 support.

### Breaking changes

Since Gradle 5.0, plugins are no longer allowed to register tasks with same name as Gradle internal tasks, such as `init`/`build`. 
Most of the tasks are renamed as follows:

|                          |                          | 
|--------------------------|--------------------------| 
| clean                    | goClean                  | 
| prepare                  | goPrepare                | 
| showGopathGoroot         | showGopathGoroot         | 
| init                     | goInit                   | 
| resolveBuildDependencies | resolveBuildDependencies | 
| resolveTestDependencies  | resolveTestDependencies  | 
| installDependencies      | installDependencies      | 
| dependencies             | goDependencies           | 
| vendor                   | goVendor                 | 
| lock                     | goLock                   | 
| build                    | goBuild                  | 
| test                     | goTest                   | 
| coverage                 | goCover                  | 
| vet                      | goVet                    | 
| fmt                      | gofmt                    | 
| check                    | goCheck                  | 

Please be aware of this change and consult [Tasks](https://github.com/gogradle/gogradle/blob/v0.10.3/docs/tasks.md) for more details.

### Fixed bugs

[etcd dependency creates near infinite vendor folder hierarchy](https://github.com/gogradle/gogradle/issues/274)