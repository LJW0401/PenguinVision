# 开始项目

## 创建工作空间
- 首先在要创建工作空间的文件夹中新建了src文件夹用来存放项目的相关代码。
- 然后在工作空间文件夹中打开终端，输入 `colcon build` 即可完成工作空间的初始化。

## 创建软件包
在src文件夹下创建一个新的用于Python的基本的软件包：
```
ros2 pkg create --build-type ament_python my_package
```

## 创建自定义消息类型
- 新建一个`interfaces`文件夹用来存放自定义的消息类型
- 编辑`CMakeLists.txt`
    ```cmake
    cmake_minimum_required(VERSION 3.8)
    project(interfaces)

    if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    add_compile_options(-Wall -Wextra -Wpedantic)
    endif()

    # find dependencies
    find_package(ament_cmake REQUIRED)
    find_package(rosidl_default_generators REQUIRED)
    find_package(geometry_msgs REQUIRED)

    rosidl_generate_interfaces(${PROJECT_NAME}
    "msg/Armor.msg"
    "msg/Armors.msg"
    《这里填各种自定义类型的文件》

    DEPENDENCIES
        std_msgs
        geometry_msgs
        《这里填各种用到的类型》
    )


    ament_package()
    ```
- 编写`package.xml`
    ```xml
    <?xml version="1.0"?>
    <?xml-model href="http://download.ros.org/schema/package_format3.xsd" schematypens="http://www.w3.org/2001/XMLSchema"?>
    <package format="3">
    <name>interfaces</name>
    <version>0.0.0</version>
    <description>TODO: Package description</description>
    <maintainer email="1357482552@qq.com">penguin</maintainer>
    <license>TODO: License declaration</license>

    <buildtool_depend>ament_cmake</buildtool_depend>

    <build_depend>rosidl_default_generators</build_depend>
    <exec_depend>rosidl_default_runtime</exec_depend>
    <member_of_group>rosidl_interface_packages</member_of_group>

    <depend>geometry_msgs</depend>
    。。。

    <export>
        <build_type>ament_cmake</build_type>
    </export>
    </package>
    ```