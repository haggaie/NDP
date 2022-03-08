executables = 'htsim_tcp htsim_ndp htsim_dctcp_permutation htsim_ndp_permutation htsim_ndp_random htsim_ndp_permutation_lossless htsim_ndp_permutation_fail htsim_ndp_incast htsim_ndp_incast_shortflows htsim_ndp_incast_collateral htsim_ndp_outcast htsim_ndp_outcast_shortflows htsim_tcp_permutation htsim_tcp_perm_shortflows htsim_ndp_perm_shortflows htsim_tcp_incast_shortflows htsim_dctcp_permutation_lossless htsim_ndp_incast_shortflows_lossless htsim_dctcp_incast_shortflows htsim_dctcp_random_shortflows htsim_dctcp_random_shortflows_lossless htsim_dctcp_perm_shortflows htsim_dctcp_perm_shortflows_lossless htsim_ndp_random_shortflows htsim_ndp_oversubscribed htsim_dctcp_oversubscribed htsim_ndp_in_out htsim_dctcp_incast_collateral htsim_dctcp_incast_collateral_lossless htsim_ndptunnel_permutation htsim_ndptunnel_incast_shortflows'.split()

datacenter_sources = 'firstfit.cpp vl2_topology.cpp fat_tree_topology.cpp bcube_topology.cpp connection_matrix.cpp oversubscribed_fat_tree_topology.cpp shortflows.cpp multihomed_fat_tree_topology.cpp star_topology.cpp'.split()

libdatacenter = static_library('datacenter', datacenter_sources,
    dependencies: [libhtsim_dep])
libdatacenter_dep = declare_dependency(
    link_with: libdatacenter,
    include_directories: include_directories('.'),
)

foreach name : executables
    executable(name, name.replace('htsim_', 'main_') + '.cpp',
        dependencies: [libhtsim_dep, libdatacenter_dep])
endforeach