# ClassConflictCheck

用于检测多个Jar包冲突的class

当一个项目使用的jar包较多时，代码经常在运行的时候抛出异常：java.lang.NoSuchMethodException，java.lang.ClassNotFoundException，基本是存在多个jar包包含相同的class类文件导致的，运行期引用的class由于版本没对上导致没有该方法等

该小工具可以帮助你检测出classpath下，通常是项目的lib目录下是否存在类冲突，且告诉你冲突的jar包，方便定位处理。

使用说明，示例：

cd liq/util
javac ClassConflictCheck.java
java ClassConflictCheck xxx/WEB-INF/lib

如果没有任何类冲突，则输出:
"oh,good! there are no class conflict in the jars"

否则则有类似如下的冲突输出 （两处冲突了）：

Class conflict!!! the class :org/aspectj/weaver/tools/MatchingContext.class has been duplicate inclusioned in the jars : [aspectjweaver-1.6.6.jar, eclipse.aspectj__aspectjweaver-1.5.2a.jar-0.0.0.jar, aspectjtools-1.6.2.jar, aspectjweaver-1.6.2.jar]
Class conflict!!! the class :org/apache/batik/css/engine/value/css2/FontSizeAdjustManager.class has been duplicate inclusioned in the jars : [xml.xmlgraphics-1.7.jar, xml.xmlgraphics__batik-css-1.7.jar-1.7.jar]


