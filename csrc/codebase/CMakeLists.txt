# Copyright (c) OpenMMLab. All rights reserved.
cmake_minimum_required(VERSION 3.14)
project(mmdeploy_codebase)

set(CODEBASES "")
if ("all" IN_LIST MMDEPLOY_CODEBASES)
    list(APPEND CODEBASES "mmcls")
    list(APPEND CODEBASES "mmdet")
    list(APPEND CODEBASES "mmseg")
    list(APPEND CODEBASES "mmocr")
    list(APPEND CODEBASES "mmedit")
else()
    set (CODEBASES ${MMDEPLOY_CODEBASES})
endif ()

foreach (codebase IN LISTS CODEBASES)
    message(STATUS "build codebase: ${codebase}")
    add_subdirectory(${codebase})
endforeach ()
