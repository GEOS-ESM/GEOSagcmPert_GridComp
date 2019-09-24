esma_set_this ()

set (SRCS
  model/a2b_edge_nlm.F90
  model/boundary_nlm.F90
  model/dyn_core_nlm.F90
  model/fastexp_nlm.c
  model/fv_arrays_nlm.F90
  model/fv_cmp_nlm.F90
  model/fv_control_nlm.F90
  model/fv_dynamics_nlm.F90
  model/fv_fill_nlm.F90
  model/fv_grid_utils_nlm.F90
  model/fv_mapz_nlm.F90
  model/fv_nesting_nlm.F90
  model/fv_sg_nlm.F90
  model/fv_tracer2d_nlm.F90
  model/fv_update_phys_nlm.F90
  model/lin_cloud_microphys_nlm.F90
  model/nh_core_nlm.F90
  model/nh_utils_nlm.F90
  model/sw_core_nlm.F90
  model/tp_core_nlm.F90

  tools/external_ic_nlm.F90
  tools/external_sst_nlm.F90
  tools/fv_diagnostics_nlm.F90
  tools/fv_eta_nlm.F90
  tools/fv_grid_tools_nlm.F90
  tools/fv_io_nlm.F90
  tools/fv_mp_nlm_mod.F90
  tools/fv_nudge_nlm.F90
  tools/fv_restart_nlm.F90
  tools/fv_surf_map_nlm.F90
  tools/fv_timing_nlm.F90
  tools/fv_treat_da_inc_nlm.F90
  tools/init_hydro_nlm.F90
  tools/sim_nc_nlm_mod.F90
  tools/sorted_index_nlm.F90
  tools/test_cases_nlm.F90

  model_tlmadm/a2b_edge_adm.F90
  model_tlmadm/a2b_edge_tlm.F90
  model_tlmadm/boundary_adm.F90
  model_tlmadm/boundary_tlm.F90
  model_tlmadm/dyn_core_adm.F90
  model_tlmadm/dyn_core_tlm.F90
  model_tlmadm/fv_arrays_tlmadm.F90
  model_tlmadm/fv_control_tlmadm.F90
  model_tlmadm/fv_dynamics_adm.F90
  model_tlmadm/fv_dynamics_tlm.F90
  model_tlmadm/fv_grid_utils_adm.F90
  model_tlmadm/fv_grid_utils_tlm.F90
  model_tlmadm/fv_mapz_adm.F90
  model_tlmadm/fv_mapz_tlm.F90
  model_tlmadm/fv_mp_adm.F90
  model_tlmadm/fv_mp_tlm.F90
  model_tlmadm/fv_nesting_adm.F90
  model_tlmadm/fv_nesting_tlm.F90
  model_tlmadm/fv_pressure.F90
  model_tlmadm/fv_restart_adm.F90
  model_tlmadm/fv_restart_tlm.F90
  model_tlmadm/fv_sg_tlm.F90
  model_tlmadm/fv_sg_adm.F90
  model_tlmadm/fv_tracer2d_adm.F90
  model_tlmadm/fv_tracer2d_tlm.F90
  model_tlmadm/nh_core_adm.F90
  model_tlmadm/nh_core_tlm.F90
  model_tlmadm/nh_utils_adm.F90
  model_tlmadm/nh_utils_tlm.F90
  model_tlmadm/sw_core_adm.F90
  model_tlmadm/sw_core_tlm.F90
  model_tlmadm/tp_core_adm.F90
  model_tlmadm/tp_core_tlm.F90

  geos_utils/fill_corner.F90
  geos_utils/flow_proj.F90
  geos_utils/ghost_cubsph.F90
  geos_utils/grid_utils_mod.F90
  geos_utils/cub2latlon.F90
  geos_utils/cub2cub.F90

)

esma_add_library (${this}
  SRCS ${SRCS}
  DEPENDENCIES MAPL_Base GFDL_fms_r8 Tapenade
  )

target_compile_definitions (${this} PRIVATE MAPL_MODE SPMD TIMING USE_COND MAIST_CAPPA OLDMPP)
esma_fortran_generator_list(${this} ${FREAL8})


  
