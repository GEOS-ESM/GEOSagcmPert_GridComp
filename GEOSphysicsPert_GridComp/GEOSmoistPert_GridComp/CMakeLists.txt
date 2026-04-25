esma_set_this ()

set (SRCS 
  GEOS_MoistPertGridComp.F90
  cloud.F90
  cloud_ad.F90
  cloud_tl.F90
  convection.F90
  convection_ad.F90
  convection_tl.F90
  qsat_util.F90
  )

if(CMAKE_Fortran_COMPILER_ID STREQUAL "GNU")
esma_add_library (${this}
  SRCS ${SRCS}
  DEPENDENCIES MAPL GEOS_Shared GEOS_PertShared fvdycorepert ${LAPACK_LIBRARIES} ${BLAS_LIBRARIES}
  )
else()
esma_add_library (${this}
  SRCS ${SRCS}
  DEPENDENCIES MAPL GEOS_Shared GEOS_PertShared fvdycorepert
  )
endif()
