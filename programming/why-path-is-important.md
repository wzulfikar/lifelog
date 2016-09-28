so, i've this friend that wants me to help her install stuffs to develop cordova hybrid mobile app.

issued this things in her cmd:

- `node -v` check if node is installed
- `npm -v` check if npm is installed
- `cordova` check if cordova is installed. if not, do `npm i -g cordova`
- `git -v` check if git is installed
- `android` check if android sdk is installed

she said she had "file cannot be moved" error when she install android sdk. since `android` is not recognized in her cmd, most likely because she didn't set up path and environment variables properly. 

checked env variables of her laptop, turns out that it has no `ANDROID_HOME`. tools and platform-tools of android sdk are not in `PATH` either. i created `ANDROID_HOME`, add path to platform-tools and tools, and issued `android` in her cmd to verify if it can detect it or not. and yes, it can handle `android` as well as `adb`, `emulate`, etc since i've added it in her system's path.

however, when i run `android`, it encounter "xcopy not recognized" error. after some googling, turns out that it requires additional paths to be added in `PATH`: `%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;`. here is the original thread: http://stackoverflow.com/a/18309881

after adding above path, the `android` command run smoothly without any error.

understanding the concept of environment variable and path is crucial when it comes to setting up development workspace.
