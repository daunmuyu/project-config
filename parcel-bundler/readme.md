# Parcel需要为零配置付出代价
零配置其实是把各种常见的场景做为默认值来实现的，这虽然能节省很多工作量，快速上手，但这同时会带来一些问题：
不守规矩的node_module：有些依赖的库在发布到Npm上时可能不小心把.babelrcpostcss.config.js tsconfig.json这些配置文件也一起发布上去了，
由于目前Parcel只要在目录中发现这些配置文件就会认为该项目中的代码需要被处理。例如mini-store这个库中就把.babelrc文件发布到了Npm上，项目依赖的本来是lib中已经编译成了ES5的JS代码了，但Parcel还会去用Babel处理一遍。
Npm官方并没有规定发布到Npm上的包需要符合哪些规范，这会让Parcel很为难。
不灵活的配置：零配置的Parcel关闭了很多配置项，在一些需要的配置的场景下无法改变。例如：
无法控制对部分文件的特殊处理，以实现诸如按需加载这样的需求；
无法控制输出文件名的Hash值和名称；
无法控制构建输出目录结构；
无法映射路径以缩短导入语句；
HTTP开发服务器不支持HistoryApi；

# Parcel使用场景受限
目前Parcel只能用来构建用于运行在浏览器中的网页，这也是他的出发点和专注点。
在软件行业不可能存在即使用简单又可以适应各种场景的方案，就算所谓的人工智能也许能解决这个问题，但人工智能不能保证100%的正确性。

反观Webpack除了用于构建网页，还可以做：

# 打包发布到Npm上的库
构建Node.js应用(同构应用)
构建Electron应用
构建离线应用(ServiceWorkers)
构建速度和输出文件大小对比
分别去用Parcel和Webpack构建以上项目，收集的数据如下：

# 数据项	Parcel	Webpack
生成环境构建时间	8.310s	9.58s
开发环境启动时间	5.42s	8.06s
监听变化构建时间	3.17s	2.87s
生成环境输出JS文件大小	544K	274K
生成环境输出CSS文件大小	23K	23K
从以上数据可以看出：Parcel构建速度快，但Parcel输出文件大

# 导致Parcel构建速度快的原因和iOS比Android用起来更流畅的原因类似：

# Parcel因为一体化内置，所以集成和优化的更好，而Webpack通过插件和Loader机制去让第三方扩展这会拉低性能；
Parcel内置多进程并行构建，而Webpack默认是单进程构建（Webpack也支持多进程）；
导致Parcel输出JS文件大的原因在于：

# 不支持TreeShaking
构建出的JS中出现了所有文件的名称，如图：
![](https://user-images.githubusercontent.com/5773264/34382680-8bd638e0-eb4b-11e7-9edf-9cbdf5c36b93.png)

# 总结
现阶段的Parcel就像beta版的iPhone，看上去很美好但还不能用于生成环境，如果你现在就把Parcel用于生成环境，相信我你一定会踩很多坑。
踩坑不要紧，要命的是无法在网上找到解决方法以快速解决问题。


