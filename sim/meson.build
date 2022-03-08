project('sim', 'cpp')

htsim_sources = 'eventlist.cpp tcppacket.cpp pipe.cpp queue.cpp queue_lossless.cpp queue_lossless_input.cpp queue_lossless_output.cpp ecnqueue.cpp tcp.cpp dctcp.cpp mtcp.cpp loggers.cpp logfile.cpp clock.cpp config.cpp network.cpp qcn.cpp exoqueue.cpp randomqueue.cpp cbr.cpp cbrpacket.cpp sent_packets.cpp ndp.cpp ndppacket.cpp eth_pause_packet.cpp tcp_transfer.cpp tcp_periodic.cpp compositequeue.cpp prioqueue.cpp cpqueue.cpp ndp_transfer.cpp compositeprioqueue.cpp switch.cpp dctcp_transfer.cpp fairpullqueue.cpp route.cpp ndptunnel.cpp ndptunnelpacket.cpp spraytunnel.cpp'

libhtsim = static_library('htsim', htsim_sources.split())
libhtsim_dep = declare_dependency(
    link_with: libhtsim,
    include_directories: include_directories('.'),
)

message('@0@'.format(libhtsim_dep))

executable('htsim', ['main.cpp'], dependencies: libhtsim_dep)
executable('parse_output', ['parse_output.cpp'], dependencies: libhtsim_dep)

subdir('datacenter')