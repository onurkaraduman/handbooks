# Troubleshooting
*Problem*
Error: ENOSPC: System limit for number of file watchers reached, watch
https://github.com/gatsbyjs/gatsby/issues/11406

*Solution*
```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

*Problem*
Error: Inside ActionBarComponent but no Page found in DI
https://github.com/NativeScript/nativescript-angular/issues/1441

*Solution*
```
At the bottom of main.ts change

platformNativeScriptDynamic().bootstrapModule(AppComponentModule);

to

platformNativeScriptDynamic({createFrameOnBootstrap: true}).bootstrapModule(AppComponentModule);
```

*Problem*
```
$ ng generate component bottomBar
An unhandled exception occurred: Cannot find module '@schematics/angular/utility/parse-name'
```

*Solution*

```
npm install  @nativescript/schematics --save
npm install @angular/cli --save
```
