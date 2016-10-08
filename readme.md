CTMediator
==========

[iOS应用架构谈 组件化方案](http://casatwy.com/iOS-Modulization.html)

`Category`目录在实际工程中是单独的一个repo，调用者通过依赖category这个repo来完成功能调度。一般来说是每一个业务对应一个category的repo。因此调用者需要调度哪个业务，就依赖哪个业务的category。category这个repo由对应提供服务的业务来维护。

`CTMediator`目录在实际工程中也是一个单独的repo，仅用于存放中间件。被每一个业务线各自维护的category repo所依赖。

`DemoModule`目录是实际提供服务的业务，这个在实际工程中也是一个单独的repo。这个repo不被任何人所依赖，这个repo通过target-action来提供被调度的功能，然后由category repo通过runtime调度。

