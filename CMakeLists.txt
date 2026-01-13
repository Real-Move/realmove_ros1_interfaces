cmake_minimum_required(VERSION 3.5)
project(realmove_ros1_interfaces)

find_package(catkin REQUIRED COMPONENTS
    roscpp
    rospy
    message_generation
    actionlib_msgs
    std_msgs
    sensor_msgs
    geometry_msgs
    dynamic_reconfigure
)

# Generate messages in the 'msg' folder
add_message_files(
    FILES
        ArucoMarker.msg
        ArucoMarkerArray.msg
        Keypoint.msg
        Skeleton.msg
        SkeletonArray.msg
        Object.msg
        ObjectArray.msg
        SkeletonDescriptionArray.msg
        SkeletonJointStateArray.msg
        Action.msg
        ActionArray.msg
        ActionAnalysis.msg
        ActionAnalysisArray.msg
        ActionFeedback.msg
        Identity.msg
        IdentityArray.msg
)

## Generate services in the 'srv' folder
add_service_files(
    FILES
        String.srv
)

## Generate actions in the 'action' folder
add_action_files( DIRECTORY action
    FILES
        Calibrate.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
    DEPENDENCIES
        std_msgs
        sensor_msgs
        geometry_msgs
        actionlib_msgs
)

catkin_package(
    CATKIN_DEPENDS 
        message_runtime
        actionlib_msgs
        dynamic_reconfigure
)
