# 策略配置文件详解
name: 这个策略的名字 可包含是谁提出的标准  
id: 策略ID,尽量不要和现有策略重名,否则如果同一服务端载入了相同策略ID的配置文件,服务端会以最先载入的配置文件为准。  
policy节点:  
(policy子节点开始)  
official 代表官方制品,默认为true,在下载的判定模型和引述文件中匹配相应的官方制品。如果服务端的全局配置文件中的online字段设为true,那么将会联网匹配(Google和Bing范围。如果填入了taobao字段中的cookie,将会在淘宝网中匹配)。  
second-print 二次印刷制品,默认为false,执行方法如上所示。  
copy 临摹作品制品,默认为true,执行方法如上所示。  
ai AI生成/辅助作品制品,默认为false,如果填写了ali-api字段中的AccessKey ID和AccessKey Secret将会调用阿里云的检测API,否则调用少量引述文件判定。  
(policy子节点结束)  
range节点:  
(range子节点开始)  
official 代表官方制品的对应配置引擎的最大检测标准。  
second-print 代表二印的对应配置引擎的判定度的最大容忍标准。  
copy 代表临摹作品的对应配置引擎的判定度的最大容忍标准。  
ai 代表AI生成/辅助作品的对应配置引擎的判定度的最大容忍标准。  
(range子节点结束)  
text-engine: 对应制品名称和描述的匹配引擎,可选mapreduce (Hadoop MapReduce),spark (Apache Spark),flink (Apache Flink)。  
image-engine: 对应制品图片的图像匹配引擎,可选opencv和matlab。  
