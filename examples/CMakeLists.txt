function(new_test name game files)
  set(projname ${name}_${game})

  add_library(${projname} SHARED ${files} ${ARGN})
  set_target_properties(${projname} PROPERTIES SUFFIX ".asi")
  target_include_directories(${projname} PRIVATE .)

  if (game STREQUAL "III")
    target_link_libraries(${projname} PRIVATE pluginsdk::gta3)
  elseif (game STREQUAL "SA")
    target_link_libraries(${projname} PRIVATE pluginsdk::gtasa)
  elseif(game STREQUAL "VC")
    target_link_libraries(${projname} PRIVATE pluginsdk::gtavc)
  endif()
endfunction()

add_subdirectory(ColouredObjects)
add_subdirectory(CreateCar)
add_subdirectory(DXFont)
add_subdirectory(FullNitrousControl)
add_subdirectory(GPS)
add_subdirectory(HandSignals)
add_subdirectory(Neon)
add_subdirectory(OpenDoorExample)
add_subdirectory(PedPainting)
add_subdirectory(PedSpawner)
add_subdirectory(PlayerWeapon)
add_subdirectory(RotateDoor)
add_subdirectory(ScriptCommands)
add_subdirectory(Speedometer)
add_subdirectory(Texture)
add_subdirectory(TimeNotTouchingPadOpcode)
add_subdirectory(UniversalTurnlights)
add_subdirectory(VehicleRemap)
add_subdirectory(VehicleSpawner)