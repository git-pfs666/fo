<template>
	<view class="content">
		<view class="header">
			<view class="search">
				<image src="../../static/search.png"></image>
				<input class="ip" placeholder="房思琪的初恋乐园" placeholder-class="ipp" />
			</view>
			<view class="nav">
				<view style="width: 17%;" :style="{color:blue1}" @tap="reader1">推荐</view>
				<view style="width: 17%;" :style="{color:blue2}" @tap="reader2">分类</view>
				<view style="width: 17%;" :style="{color:blue3}" @tap="reader3">排行</view>
				<view style="flex: 1;" :style="{color:blue4}" @tap="reader4">文学艺术</view>
				<view style="flex: 1;" :style="{color:blue5}" @tap="reader5">哲学社科</view>
			</view>
		</view>
		<view style="box-sizing: border-box;padding-top: 180rpx;" v-show="read1">
			<view class="bookInfo" v-for="(book1,index) in bookData" :key="index">
				<view class="bookEach">
					<view class="bookImg">
						<image :src="book1.boogImg"></image>
					</view>
					<view class="bookText">
						<view class="bookName">{{book1.bookName}}</view>
						<view class="author">{{book1.author}}</view>
						<view class="popularity">{{book1.popularity}}</view>
					</view>
				</view>
			</view>
		</view>
		<view style="box-sizing: border-box;padding: 180rpx 35rpx 35rpx 35rpx;" v-show="read2">
			<view class="bookClass" v-for="(book2,index) in bookDataClass">
				<view class="bookClassText">
					<view class="bookTab">{{book2.bookTab}}</view>
					<view class="bookItem">{{book2.bookItem1}}</view>
					<view class="bookItem">{{book2.bookItem2}}</view>
					<view class="bookItem">{{book2.bookItem3}}</view>
				</view>
				<view class="bookClassImg">
					<image :src="book2.bookImg"></image>
				</view>
			</view>
		</view>
		<view style="box-sizing: border-box;padding: 180rpx 35rpx 35rpx 35rpx;" v-show="read3">
			<view class="bookRank" v-for="(book3,index) in bookDataRank">
				<view class="bookLogo">{{book3.bookLogo}}</view>
				<view class="bookEach" style="height: 150rpx;" v-for="(i,index) in book3.site">
					<view class="bookImg">
						<image :src="i.bookImg"></image>
					</view>
					<view style="width: 100%;box-sizing: border-box;padding: 20rpx 20rpx;">
						<view class="bookName" style="font-size: 30rpx;display: flex;">
							<view style="width: 7%;">{{index+1}}</view>
							<view style="flex: 1;">{{i.bookName}}</view>
						</view>
						<view class="author" style="position: relative;left: 7%;">{{i.author}}</view>
					</view>
				</view>
				<button type="default" size="mini" style="width: 100%;color: #007AFF;">查看全部</button>
			</view>
		</view>
		<view style="box-sizing: border-box;padding: 180rpx 35rpx 35rpx 0rpx;" v-show="read4">
			<view style="width: 100%;display: flex;margin: 40rpx 0;" v-for="(book4,index) in bookData4">
				<view class="index">{{index+1}}</view>
				<view class="bookEach" style="width: 90%;margin: 0;">
					<view class="bookImg">
						<image :src="book4.bookImg"></image>
					</view>
					<view class="bookText" style="width: 80%;padding: 15rpx 0 15rpx 15rpx;">
						<view class="bookName">{{book4.bookName}}</view>
						<view class="author" style="color:#7c7c7c">{{book4.author}}</view>
						<view class="popularity" style="color:#7c7c7c">{{book4.popularity}}</view>
					</view>
				</view>
			</view>
		</view>
		<view style="box-sizing: border-box;padding: 180rpx 35rpx 35rpx 0rpx;" v-show="read5">
			<view style="width: 100%;display: flex;margin: 40rpx 0;" v-for="(book5,index) in bookData5">
				<view class="index">{{index+1}}</view>
				<view class="bookEach" style="width: 90%;margin: 0;">
					<view class="bookImg">
						<image :src="book5.bookImg"></image>
					</view>
					<view class="bookText" style="width: 80%;padding: 15rpx 0 15rpx 15rpx;">
						<view class="bookName">{{book5.bookName}}</view>
						<view class="author" style="color:#7c7c7c">{{book5.author}}</view>
						<view class="popularity" style="color:#7c7c7c">{{book5.popularity}}</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				bookData:[{
					boogImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=80326913,2075562933&fm=26&gp=0.jpg',
					bookName:'傲天圣帝',
					author:'唯易永恒 | 8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2189549050,839005391&fm=26&gp=0.jpg',
					bookName:'荣耀王者',
					author:'夜雨黑 | 9分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1978167718,3903294298&fm=26&gp=0.jpg',
					bookName:'此生不负你情深',
					author:'蓝莓爱芝士 | 8.2分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1665551225,2372965066&fm=26&gp=0.jpg',
					bookName:'重生之狂暴火法',
					author:'燃烧的地狱咆哮 | 8.2分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2305833776,427844965&fm=15&gp=0.jpg',
					bookName:'宠妾作死日常',
					author:'月下微尘 | 8.2分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1163821008,1247784394&fm=11&gp=0.jpg',
					bookName:'仙武帝尊',
					author:'六界三道 | 8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1138874109,2749654572&fm=26&gp=0.jpg',
					bookName:'金庸作品集（简体新版）',
					author:'金庸 | 9.5分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1306936197,1876348585&fm=11&gp=0.jpg',
					bookName:'至尊女婿',
					author:'黄晓鸭 | 7.7分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=887904280,938737577&fm=15&gp=0.jpg',
					bookName:'碟殇之山河破碎',
					author:'沉醉四月 | 8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1117866649,1896092240&fm=26&gp=0.jpg',
					bookName:'芈月传（全6册）',
					author:'蒋胜男 | 7.8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1739188006,1123248346&fm=11&gp=0.jpg',
					bookName:'弹弓神警（独家首发）',
					author:'常书欣 | 9.1分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=80326913,2075562933&fm=26&gp=0.jpg',
					bookName:'傲天圣帝',
					author:'唯易永恒 | 8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1010063792,512556247&fm=26&gp=0.jpg',
					bookName:'宠你一世又何妨',
					author:'桃慕慕 | 7.4分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3836426729,2505784313&fm=26&gp=0.jpg',
					bookName:'丹武至尊',
					author:'顽石 | 7.8分',
					popularity:'大家都在看'
				},{
					boogImg:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586797004688&di=3ff39873f8a455e5297752939980e1bd&imgtype=0&src=http%3A%2F%2Fa4.att.hudong.com%2F80%2F60%2F01300543373111146528608616963_s.jpg',
					bookName:'斩龙',
					author:'失落叶 | 8.3分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3404455275,3598525729&fm=26&gp=0.jpg',
					bookName:'1号重案组',
					author:'毛德远 | 8.5分',
					popularity:'大家都在看'
				},{
					boogImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1721916553,2415193671&fm=15&gp=0.jpg',
					bookName:'总裁老公追上门',
					author:'唯易永恒 | 8分',
					popularity:'大家都在看'
				}],
				blue1:'#007AFF',blue2:'#007AFF',blue3:'#007AFF',blue4:'#007AFF',blue5:'#007AFF',
				read1:true,read2:false,read3:false,read4:false,read5:false,
				bookDataClass:[{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1922109286,2905328121&fm=26&gp=0.jpg',
					bookTab:'现实小说榜',
					bookItem1:'1.房思琪的初恋乐园',
					bookItem2:'2.平凡的世界（全三册）',
					bookItem3:'3.如果没有明天（《我是余欢水》原著）',
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1661757566,2566923043&fm=26&gp=0.jpg',
					bookTab:'影视原著榜',
					bookItem1:'1.庆余年',
					bookItem2:'2.鬼吹灯（盗墓者的经历）',
					bookItem3:'3.三体（全集）',
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=803344193,2442564579&fm=26&gp=0.jpg',
					bookTab:'情感小说榜',
					bookItem1:'1.你好，秦医生',
					bookItem2:'2.挪威的森林',
					bookItem3:'3.追风筝的人',
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3739685210,3295006415&fm=11&gp=0.jpg',
					bookTab:'悬疑恐怖榜',
					bookItem1:'1.侯大力刑侦笔记（独家首发）',
					bookItem2:'2.麻衣神算子',
					bookItem3:'3.麻衣神相',
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2189549050,839005391&fm=26&gp=0.jpg',
					bookTab:'玄幻精品榜',
					bookItem1:'1.荣耀王者',
					bookItem2:'2.雪中焊刀行',
					bookItem3:'3.龙族（1-4集）',
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1008347803,2033790745&fm=26&gp=0.jpg',
					bookTab:'经典小说榜',
					bookItem1:'1.百年孤独',
					bookItem2:'2.霍乱时期的爱情',
					bookItem3:'3.红楼梦',
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2189549050,839005391&fm=26&gp=0.jpghttps://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3504023743,693776329&fm=26&gp=0.jpg',
					bookTab:'科幻经典榜',
					bookItem1:'1.三体（全集）',
					bookItem2:'2.三体前传：球状闪电',
					bookItem3:'3.海奥华预言',
				},{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3163712308,368712465&fm=26&gp=0.jpg',
					bookTab:'武侠经典榜',
					bookItem1:'1.古龙：楚留香前传（全4册）',
					bookItem2:'2.古龙作品大全集（72册）',
					bookItem3:'3.天龙八部（全五册）',
				},{
					bookImg:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586797519442&di=b740a1f17c1213e52df1b5ab88c09a5b&imgtype=0&src=http%3A%2F%2Fwx4.sinaimg.cn%2Forj360%2F007hzHORly1gdfae70g7sj309m0dwab6.jpg',
					bookTab:'文学艺术榜',
					bookItem1:'1.半小时漫画宋词（独家首发）',
					bookItem2:'2.云边有个小卖部',
					bookItem3:'3.蒋勋说红楼梦（套装共8册）',
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2137979940,2539709046&fm=26&gp=0.jpg',
					bookTab:'个人成长榜',
					bookItem1:'1.非暴力沟通',
					bookItem2:'2.亲密关系',
					bookItem3:'3.原则',
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1487928739,1945550420&fm=11&gp=0.jpg',
					bookTab:'哲学社科榜',
					bookItem1:'1.被讨厌的勇气',
					bookItem2:'2.墨菲定律',
					bookItem3:'3.天才在左，疯子在右',
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1703938262,3974694278&fm=26&gp=0.jpg',
					bookTab:'历史榜',
					bookItem1:'1.明朝那些事儿（全集）',
					bookItem2:'2.人类简史（新版）',
					bookItem3:'3.大唐兴亡三百年（全集）',
				},{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1516734913,433140084&fm=26&gp=0.jpg',
					bookTab:'生活榜',
					bookItem1:'1.这书能让你戒烟',
					bookItem2:'2.女生呵护指南',
					bookItem3:'3.只有医生知道！',
				}],
				bookDataRank:[{
					bookLogo:'飙升',
					site:[{
						bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1803060161,3845361995&fm=11&gp=0.jpg',
						bookName:'如果没有明天（《我是余欢水》原著）',
						author:'余耕'
					},{
						bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1243261942,1033883979&fm=26&gp=0.jpg',
						bookName:'黑少，你老婆又在装傻',
						author:'今歌'
					},{
						bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=571214360,4235159247&fm=26&gp=0.jpg',
						bookName:'舟而复始（《致我们甜甜的小美满》原著）',
						author:'赵乾乾'
					}]
				},{
					bookLogo:'新书',
					site:[{
						bookImg:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=973606148,1915385877&fm=11&gp=0.jpg',
						bookName:'沉默的巡游',
						author:'东野圭吾'
					},{
						bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1765901083,3035580316&fm=11&gp=0.jpg',
						bookName:'半小时漫画宋词（独家首发）',
						author:'陈嘉·半小时漫画团队'
					},{
						bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=803344193,2442564579&fm=26&gp=0.jpg',
						bookName:'你好，秦医生',
						author:'夜蔓'
					},{
						bookImg:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586833401929&di=0957f63ecf07198137e0bf0843c181ca&imgtype=0&src=http%3A%2F%2Fstatics.zhuishushenqi.com%2Fagent%2Fhttp%3A%2F%2Fimg.1391.com%2Fapi%2Fv1%2Fbookcenter%2Fcover%2F1%2F2174215%2F2174215_6d5776adaf514dc38bbd3ccecbc45668.jpg%2F',
						bookName:'武神主宰',
						author:'暗魔师'
					}]
				},{
					bookLogo:'总榜',
					site:[{
						bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=834783434,178325998&fm=26&gp=0.jpg',
						bookName:'人类简史（新版）：从动物到上帝',
						author:'尤瓦尔·赫拉利'
					},{
						bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=265800790,1715649885&fm=26&gp=0.jpg',
						bookName:'百年孤独',
						author:'加西亚·马尔克斯'
					},{
						bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=765093838,240984918&fm=26&gp=0.jpg',
						bookName:'蒋勋说红楼梦',
						author:'蒋勋'
					},{
						bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1854334830,3338501606&fm=26&gp=0.jpg',
						bookName:'平凡的世界（全三册）',
						author:'路遥'
					}]
				}],
				bookData4:[{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1765901083,3035580316&fm=11&gp=0.jpg',
					bookName:'半小时漫画宋词（独家首发）',
					author:'陈磊·半小时漫画团队',
					popularity:'8.2 8653人今日在读'
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1630620057,320171220&fm=26&gp=0.jpg',
					bookName:'云边有个小卖部',
					author:'张嘉佳',
					popularity:'9.4 3818人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=765093838,240984918&fm=26&gp=0.jpg',
					bookName:'蒋勋说红楼梦',
					author:'蒋勋',
					popularity:'9.4 3697人今日在读'
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1138874109,2749654572&fm=26&gp=0.jpg',
					bookName:'金庸作品集（简体新版）',
					author:'金庸',
					popularity:'9.5 3432人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=997093404,1061909598&fm=26&gp=0.jpg',
					bookName:'邓小平时代',
					author:'傅高义',
					popularity:'9.1 3214人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3372836294,2243131807&fm=26&gp=0.jpg',
					bookName:'曾国藩：唐浩明修订版（全集）',
					author:'唐浩明',
					popularity:'8.9 3011人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3825376866,2220708035&fm=26&gp=0.jpg',
					bookName:'撒哈拉的故事',
					author:'三毛',
					popularity:'9.3 2757人今日在读'
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2478922477,2339406845&fm=26&gp=0.jpg',
					bookName:'看见',
					author:'柴静',
					popularity:'8.9 2731人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3154695308,1051125098&fm=26&gp=0.jpg',
					bookName:'历史的温度（全四册-独家定制版）',
					author:'张玮',
					popularity:'9.4 2587人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=4169384562,3617825012&fm=26&gp=0.jpg',
					bookName:'人间失格',
					author:'太宰治',
					popularity:'9.1 2566人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3862190831,677856401&fm=26&gp=0.jpg',
					bookName:'平均分',
					author:'唐辉',
					popularity:'9.3 2284人今日在读'
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1659425525,2604855292&fm=26&gp=0.jpg',
					bookName:'那不勒斯四部曲',
					author:'埃莱娜·费兰特',
					popularity:'7.7 2170人今日在读'
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2009670277,1681423789&fm=26&gp=0.jpg',
					bookName:'沉默的大多数',
					author:'玉小波',
					popularity:'9.1 2017人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2584247206,1986751565&fm=26&gp=0.jpg',
					bookName:'皮囊',
					author:'白岩松',
					popularity:'8.7 1906人今日在读'
				}],
				bookData5:[{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1634979985,4145484417&fm=26&gp=0.jpg',
					bookName:'被讨厌的勇气',
					author:'岸见一郎 古贺史健',
					popularity:'9.4 5077人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1852599029,2858403855&fm=26&gp=0.jpg',
					bookName:'墨菲定律',
					author:'李原',
					popularity:'9.2 3268人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3811643789,3205352604&fm=26&gp=0.jpg',
					bookName:'天才在左 疯子在右',
					author:'高铭',
					popularity:'9.2 2909人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1797856049,2044293635&fm=26&gp=0.jpg',
					bookName:'天空的另一半',
					author:'克里斯多夫 雪莉·邓恩',
					popularity:'9.0 2826人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2131843364,1567034800&fm=26&gp=0.jpg',
					bookName:'自控力',
					author:'凯丽·麦格尼格尔',
					popularity:'9.1 2254人今日在读'
				},{
					bookImg:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1350561433,2274701629&fm=26&gp=0.jpg',
					bookName:'道德经',
					author:'老子 李若水译评',
					popularity:'8.9 2248人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3697092701,511098601&fm=26&gp=0.jpg',
					bookName:'自卑与超越',
					author:'阿尔弗雷德·阿德勒',
					popularity:'9.0 1638人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=704701945,1699907147&fm=26&gp=0.jpg',
					bookName:'乌合之众：大众心里研究',
					author:'勒庞',
					popularity:'8.9 1520人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3951221479,3663396740&fm=26&gp=0.jpg',
					bookName:'未来简史：从智人到智神',
					author:'尤瓦尔·赫拉利',
					popularity:'9.1 1447人今日在读'
				},{
					bookImg:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2847364792,1364392521&fm=26&gp=0.jpg',
					bookName:'血疫：埃博拉的故事',
					author:'理查德·普雷斯顿',
					popularity:'9.3 1437人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3229423820,3176127692&fm=11&gp=0.jpg',
					bookName:'人生十二法则',
					author:'乔丹·彼得森',
					popularity:'9.3 1356人今日在读'
				},{
					bookImg:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=832603033,666436127&fm=26&gp=0.jpg',
					bookName:'原生家庭',
					author:'苏珊·福沃德博士 克雷格·巴克',
					popularity:'9.1 1349人今日在读'
				},{
					bookImg:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586836588814&di=9a4c9eca41b2faa70dd5621d85c64af3&imgtype=0&src=http%3A%2F%2Fcdnimg103.lizhi.fm%2Falbum_cover%2F2017%2F01%2F07%2F2578209990444424220_320x320.jpg',
					bookName:'人生的智慧',
					author:'叔本华',
					popularity:'9.2 1330人今日在读'
				},{
					bookImg:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2283982853,2550555500&fm=26&gp=0.jpg',
					bookName:'娱乐至死',
					author:'尼尔·波兹曼',
					popularity:'9.2 1269人今日在读'
				}]
			}
		},
		methods: {
			reader1(){
				this.read1=true,
				this.read2=false,
				this.read3=false,
				this.read4=false,
				this.read5=false,
				this.blue1="#007AFF",
				this.blue2='black',
				this.blue3='black',
				this.blue4='black',
				this.blue5='black'
			},
			reader2(){
				this.read1=false,
				this.read2=true,
				this.read3=false,
				this.read4=false,
				this.read5=false,
				this.blue1="black",
				this.blue2='#007AFF',
				this.blue3='black',
				this.blue4='black',
				this.blue5='black'
			},
			reader3(){
				this.read1=false,
				this.read2=false,
				this.read3=true,
				this.read4=false,
				this.read5=false,
				this.blue1="black",
				this.blue2='black',
				this.blue3='#007AFF',
				this.blue4='black',
				this.blue5='black'
			},
			reader4(){
				this.read1=false,
				this.read2=false,
				this.read3=false,
				this.read4=true,
				this.read5=false,
				this.blue1="black",
				this.blue2='black',
				this.blue3='black',
				this.blue4='#007AFF',
				this.blue5='black'
			},
			reader5(){
				this.read1=false,
				this.read2=false,
				this.read3=false,
				this.read4=false,
				this.read5=true,
				this.blue1="black",
				this.blue2='black',
				this.blue3='black',
				this.blue4='black',
				this.blue5='#007AFF'
			},
		},
		computed:{
			getHeight(){
				var gd;
				uni.getSystemInfo({
					success: (res) => {
						gd=res.windowHeight-180-40+'rpx'
						console.log(gd)
					}
				})
				return gd
			}
		},
		onShow() {
			console.log(this.getHeight)
		},
		onLoad(){
			this.read1=true,
			this.blue1="#007AFF",
			this.blue2='black',
			this.blue3='black',
			this.blue4='black',
			this.blue5='black'
		}
	}
</script>

<style>
	page{
		padding: 0;
		margin: 0;
	}
	.content{
		padding: 0 25rpx 25rpx 25rpx;
		width: 100%;
		box-sizing: border-box;
		height: auto;
		position: relative;
	}
	.header{
		width: 93%;
		box-sizing: border-box;
		height: 180rpx;
		display: flex;
		flex-wrap: wrap;
		position: fixed;
		flex-direction: column;
		background-color: white;
		z-index: 2;
	}
	.search{
		flex: 1;
		position: relative;
	}
	.ip{
		padding-left: 70rpx;
		box-sizing: border-box;
		width: 100%;
		height: 70rpx;
		margin: 10rpx 0;
		border: none;
		background-color: #eeeeee;
		border-radius: 30rpx;
	}
	.search image{
		width: 55rpx;
		height: 50rpx;
		top: 20rpx;
		left: 15rpx;
		position: absolute;
	}
	.ipp{
		color: #afafaf;
	}
	.nav{
		flex: 1;
		display: flex;
	}
	.nav view{
		height: 90rpx;
		text-align: center;
		line-height: 90rpx;
		font-family: 楷体;
		color: #a7a7a7;
	}
	.bookInfo{
		width: 100%;
		position: relative;
	}
	.bookEach{
		width: 100%;
		height: 180rpx;
		display: flex;
		margin: 25rpx;
	}
	.bookImg{
		width: 20%;
		height: 100%;
	}
	.bookImg image{
		width: 100%;
		height: 100%;
	}
	.bookText{
		line-height: 40rpx;
		width: 40%;
		height: 100%;
		box-sizing: border-box;
		padding: 35rpx 0 15rpx 25rpx;
	}
	.bookName{
		position: relative;
		font-size: 34rpx;
	}
	.author,.popularity{
		font-size: 23rpx;
		color: #bababa;
	}
	.bookClass{
		width: 100%;
		height: 230rpx;
		border-radius: 30rpx;
		margin: 30rpx 0;
		display: flex;
		background-color: #f4f4f4;
		overflow: hidden;
	}
	.bookClassText{
		width: 75%;
		height: 100%;
	}
	.bookClassImg{
		width:25%;
		height: 100%;
	}
	.bookTab{
		font-size: 40rpx;
		position: relative;
		top: 30rpx;
		left: 30rpx;
	}
	.bookItem{
		font-size: 25rpx;
		position: relative;
		top: 25rpx;
		left: 30rpx;
		margin: 10rpx 0;
		color: #888888;
	}
	.bookClassImg image{
		width: 100%;
		height: 100%;
	}
	.bookRank{
		width: 100%;
	}
	.index{
		flex: 1;
		text-align: center;
		line-height: 180rpx;
		height: 180rpx;
	}
</style>
