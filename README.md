# OTT-IPTV
移动魔百盒直播源生成m3u8播放列表
使用方法
  苏州移动IPTV抓包 获取频道列表接口地址和基础URL
  
  从下面网址中    
  http://looktvepg.jsa.bcs.ottcn.com:8080/ysten-lvoms-epg/epg/getChannelIndexs.shtml?deviceGroupId=1697
  
 可以看到
 "channel1":{"uuid":"HD-8000k-1080P-cctv1","channelName":"CCTV-1","channelIcon":"http://images.center.bcs.ottcn.com:8080/images/ysten/images/ysten/TV/HD-8000k-1080P-cctv1/CCTV-1JSXB.png"}
 的结构需要转换成  http://183.207.248.71:80/cntv/live1/channelName/uuid  的方式就可以播放了
 
 },
 },\N
 
 
 "channel[0-9]{0,9}":{"uuid":"(.*?)","channelName":"(.*?)","channelIcon":"http://images(.*?).png"}
 
 \2,http://183.207.248.71:80/cntv/live1/\2/\1
 
 
 合肥移动IPTV真实地址
合肥移动的url格式和苏州移动的格式差别不小，没有channelName，直接更改uuid即可。

所有频道列表：http://looktvepg.aha.bcs.ottcn.com:8080/ysten-lvoms-epg/epg/getChannelIndexs.shtml?deviceGroupId=924
构造URL：http://112.30.36.17:8112//120000001001/wlds:8080/ysten-business/live/uuid/1.m3u8
以CCTV-1为例，其真实地址为：http://112.30.36.17:8112//120000001001/wlds:8080/ysten-business/live/HD-8000k-1080P-cctv1/1.m3u8
