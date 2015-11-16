<h2>组件说明</h2>
　　此日期功能组件，包括日期选择器和月份选择器两类，覆盖大部分的日期选择的交互和功能，特别适合基于日期或者月份所做的配置类或数据展示类的操作，组件基于jQuery1.7.2。

<h2>文件列表</h2>
+  jquery.min.js是官方jQuery1.7.2的压缩版。
+  dateRange.js是日期选择器的主JS库。
+  dateRange.css 是日期选择器的样式列表。
+  ./images 是组件用到的图片资源。
+  sample.html 示例代码

<h2>使用说明</h2>
###调用示例（最简单的调用示例）：###
<pre>
	<code>
		var dateRange = new pickerDateRange('date_demo3', {
					isTodayValid : true,
					startDate : '2015-11-14',
					endDate : '2015-11-21',
					success : function(obj) {
						//TODO user define callback handler;
					}
				});

	</code>
</pre>
###重点参数:###
####startDate####
>这是日期选择器初始化时候，必须传入的开始日期的参数，与endDate成对出现，
>格式如:'2015-10-10'
####calendars####
>这是定义日期选择面板的月份选择栏位有多少个，默认是两个，即默认展示本月和上一个月的自然日选择。
####dayRangeMax####
>控制用户最大可选天数的范围，默认是0，即不限制，假如用户设置为30，那么日期选择器的开始日期和结束日期的最大天数跨度，不得超过30天
####isTodayValid#####
>控制今日是否可选的配置项，一般如果系统中提供实时或者今天的日期相关功能，则设置为true，默认是false
####stopToday####
>控制日期选择器的可选粒度，如果此配置项配置为true，则表示今天之后的日期将不可选择。
####isSingleDay####
>判断此日期选择器是日期复选还是单选，默然是复选，如设置为true，则此日期选择器是单选。
####weekendDis####
>有些业务场景是周末不可选的情况，将此配置项设置为true，就可以达到这个效果。
####disCertainDay####
>设置一周中周期性的某几天不可选择，如设置为[1,3]，则代表每周的周一、周三不可选择。
####disCertainDate####
>设置每个月中周期性的某几天不可选择，如设置为[5,15,25]，则代表每月的5日、15日、25日不可选择。
####shortOpr####
>日期选择是否需要确定来触发，如果不希望多一步确认的操作，则设置为true，默认是false。
####magicSelect####
>日期选择器默认切换月份和年份，只能通过向前和向后的按钮，如果希望自定义下拉选择，则可以设置为true，
>就可以通过下来选择自定义一定范围的月份和年，默认是false。
####autoCommit####
>日期选择器默认初始化后，并不会提交callback handler的事件，有一些场景希望在业务初始化完毕后就调用，
>比如某些报表系统，希望默认页面完成加载就执行查询，则可以在初始化日期选择器的时候设置为true，默认是false。
####autoSubmit####
>隐藏确定取消按钮，并且直接执行callback handler，功能等于 shorOpr:true, autoCommit:true，默认是false。
####success####
>这个是日期选择器最重要的参数之一，绑定日期切换后的回调函数，比如执行查询操作等操作。回调参数会传递当前选择的日期实体。
<h2>返回值说明</h2>
>在回调函数中会讲选择的日期实体回传，供在回调内部访问操作
<pre>
    <code>
        retObj = {
            startDate:'2015-10-10',
            endDate:'2015-10-17',
            needCompare:true,
            startCompareDate:'2015-10-01',
            endCompareDate:'2015-10-08'
        }
    </code>
</pre>
