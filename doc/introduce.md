# SDK简介
SpeechSDK是由出门问问提供的语音技术SDK，包括热词唤醒、语音识别、语义理解、垂直搜索和语音合成等组成部分。

* [功能](#%E5%8A%9F%E8%83%BD)
	* [热词唤醒](#%E7%83%AD%E8%AF%8D%E5%94%A4%E9%86%92)
	* [语音识别](#%E8%AF%AD%E9%9F%B3%E8%AF%86%E5%88%AB)
	* [语义理解](#%E8%AF%AD%E4%B9%89%E7%90%86%E8%A7%A3)
	* [垂直搜索](#%E5%9E%82%E7%9B%B4%E6%90%9C%E7%B4%A2)
	* [语音合成](#%E8%AF%AD%E9%9F%B3%E5%90%88%E6%88%90)
* [兼容性](#%E5%85%BC%E5%AE%B9%E6%80%A7)
    * [Android版](#android%E7%89%88)
    * [Linux版](#linux%E7%89%88)

## 功能
### 热词唤醒
- 支持设备在亮屏、灭屏状态下被用户语音唤醒
- 支持中英文热词，唤醒率高而误触发率低
> 在性能方面，特别针对各种平台嵌入式设备做了优化，具有较低的CPU及内存占用率。  

### 语音识别
分为在线语音识别，离线语音识别以及混合式语音识别。
 
- 在线语音识别  
	
使用[HMM (Hidden Markov Model)](https://en.wikipedia.org/wiki/Hidden_Markov_model) + [TDNN (Time Delay Neural Network)](https://en.wikipedia.org/wiki/Time_delay_neural_network)作为声学模型，在架构上优于业界普遍采用的[HMM](https://en.wikipedia.org/wiki/Hidden_Markov_model) + [DNN (Deep Neural Network)](https://en.wikipedia.org/wiki/Deep_learning#Brief_discussion_of_deep_neural_networks)。语言模型会根据搜索领域进行针对性的优化，使得语音搜索结果更准确，识别率高达95%。在用户允许的前提下，可以把联系人通讯录上传，使得在线识别联系人达到更高的准确率。
   
同时，作为Android Wear中文语音搜索的提供方以及Ticwear的开发者，我们拥有业界最多的智能硬件上采集到的语音数据，从而也使得我们针对智能硬件的语音识别准确率显著高于业界水平。
 
- 离线语音识别

和在线语音识别采用类似的算法，但为了适应嵌入式系统的有限资源，针对离线应用场景使用了单独的模型和大量的性能优化。目前主要支持语音命令识别，以及通讯录相关的识别。
 
- 混合式语音识别

通过一定的融合策略，混合离线和在线识别的结果，使得语音识别的最终结果可以更快，更准确的返回给用户。在没有网络或者网络质量很差的情况下也能完成语音指令功能，而在网络连接稳定的情况下，可以通过在线获得更通用的语音识别服务。
 
### 语义理解
对语音识别的结果进行语义分析。针对支持的约60个垂直领域进行了大量的优化，从而可以更准确的理解用户的查询需求。另外，还有提供给注册用户的个性化服务，比如语音指令“导航到公司”，后台可以根据用户公布给系统的公司位置信息进行自动补全。  

### 垂直搜索
对语音识别以及理解后的结果进行垂直领域的搜索，我们有业界最全面的互联网数据库，可以提供给用户最新，最准确的搜索信息。我们自建的搜索引擎支持约60个垂直领域，均实现了多维度的查询，比如餐馆可以支持地点、价位、无线上网等。通过NLP的精准多维度分析，结合切面搜索，能够一次性完成较为复杂的用户查询。同时，技术团队对搜索速度进行了卓有成效的优化，减少搜索延时。  

### 语音合成
采用[HMM](https://en.wikipedia.org/wiki/Hidden_Markov_model) + [DNN](https://en.wikipedia.org/wiki/Deep_learning#Brief_discussion_of_deep_neural_networks)相结合的方式进行语音合成，既保证了合成结果的稳定性，同时又提升语音的自然度，实现了业界领先的合成效果。有效的使用了离在线相结合的方式，即便在网速不理想的情况下，也可以及时给用户合成语音反馈。

在线语音合成使用了独创的**Ultra Streaming**技术，可以极速合成大量文本，让用户瞬间享受到高质量的播报服务，同时在线合成的流量低至3kB/s, 有效节约了用户的流量资源。离线语音合成针对用户设备进行了深度优化，对设备的计算资源占用极低，基本不会影响到设备的电量消耗。目前合成支持多种输出格式，包括mp3、speex格式等, 可以满足应用的多种需求。  
 
## 兼容性
### Android版     

|         平台                  |API Level | 
|------------------------------|-----------|
| armv7, armv8, mips, x86_64   |　>= 17    |



### Linux版  
支持armv7，armv8，x86_64

