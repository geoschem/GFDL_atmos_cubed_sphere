esma_set_this()

set(srcs
  ../tp_core.F90
  stubs/fv_mp_mod_stub.F90
  stubs/fv_grid_utils_stub.F90
  stubs/fv_arrays_stub.F90
  input/input_arrays.f90
  output/output_arrays.f90
  driver_cpu.f90
  main.f90)

ecbuild_add_executable(
  TARGET tp-core-driver
  SOURCES ${srcs})
target_compile_options(tp-core-driver PRIVATE ${TRACEBACK})
set_target_properties(${this} PROPERTIES Fortran_MODULE_DIRECTORY ${esma_include}/${this})
