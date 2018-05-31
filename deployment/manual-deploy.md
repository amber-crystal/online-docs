## `How can i do it manually on server?`

### In your development machine:

1. Open your production env file with `amber encrypt` then edit the port to 80 and the database URL, also disable/enable some logs if you want

2. If you have assets and you're using NPM, use `npm install . && npm run release` to compile and minify css and js

### In your production machine:

1. You will need `crystal` and `shards` command (`amber` cli tool is not required on production) . Also you can try to cross-compile to avoid install these dependencies but this feature is a bit buggy right now
Finally run your project executable with `bin/<my-project-name>` (may need sudo permission if you're using port 80 or ports < 1000)

2. Then copy your project repository and ensure to setup `AMBER_ENCRYPTION_KEY=<your-encryption-key>` and `AMBER_ENV=production` in your environments variables. You can get your encryption key from `.encryption_key` file in your development machine.
 You will need `crystal` and shards command (amber cli tool is not required on production) . Also you can try to cross-compile to avoid install these dependencies but this feature is a bit buggy right now :sweat_smile:
 
3. Then inside your project's folder, Install your project's shards with `shards install --production` and compile your executable with `shards build --release` (may take a while because `--release` enables compiler optimizations, you can avoid `--release` if you server is low end (less 256 RAM), the amber performance is still acceptable on non-release mode)

4. Finally run your project executable with `bin/<my-project-name>` (may need `sudo` permission if you're using port 80 or ports < 1000)

Optionally I would recommend you to setup a systemd service, this way you can monitor your app very easy, see: [amberframework/amberframework.org#102](https://github.com/amberframework/amberframework.org/pull/102)

Also you can configure a githook to deploy like a boss using `git push production` (just like heroku) but it requires a bit more work, I should write a guide, though  :wink:
