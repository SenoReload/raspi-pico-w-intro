if (TARGET tinyusb_device)
    add_executable(blinkSerial
            blinkSerial.c
            )

    # pull in common dependencies
    target_link_libraries(blinkSerial pico_stdlib)

    # create map/bin/hex file etc.
    pico_add_extra_outputs(blinkSerial)

elseif(PICO_ON_DEVICE)
    message(WARNING "not building blinkSerial because TinyUSB submodule is not initialized in the SDK")
endif()
