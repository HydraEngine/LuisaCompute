find_package(Vulkan)

set(LUISA_COMPUTE_VULKAN_SOURCES
        buffer.cpp
        buffer.h
        device.cpp
        device.h
        event.cpp
        event.h
        resource_barrier.cpp
        resource_barrier.h
        stream.cpp
        stream.h
        texture.cpp
        texture.h
        VulkanDevice.cpp
        VulkanDevice.h
        VulkanBuffer.cpp
        VulkanBuffer.h
        VulkanTools.cpp
        VulkanTools.h
)

luisa_compute_add_backend(vulkan SOURCES ${LUISA_COMPUTE_VULKAN_SOURCES})

target_link_libraries(luisa-compute-backend-vulkan
        PUBLIC
        luisa-compute-runtime
        Vulkan::Vulkan
        ${X11_LIBRARIES})