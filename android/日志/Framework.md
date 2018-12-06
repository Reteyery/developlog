##Framework source code##

    1、ContextImpl

        ContextImpl继承Context，context既上下文，ContextImpl中对外提供了一系列的get方法，eg:getAssert()、getResources()、ensurePrivateDirExists、getPreferencesDir。
        上下文是四大组件交互的纽带，通过上下文context,可以启动一个activity、service、发送广播等等

        ContextImpl提供了create方法创建context，包括createActivityContext、createAppContext、createSystemUiContext