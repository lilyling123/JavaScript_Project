    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8"/>
    <title>豪情前端作品列表 - 着重于原生js的研究与探索</title>
    <link rel="stylesheet" type="text/css" href="css/reset.css" media="all"/>
    <link rel="stylesheet" type="text/css" href="css/main.css" media="all"/>
    </head>
    <body>
    <!--http://1.gitapp.sinaapp.com/base/-->
    <div class="wrap shadow">
    <ol id="ol" class="list">
    
    </ol>
    </div>
    <div class="auto welcome none">
    <p>欢迎加QQ群：327388215 交流</p>
    </div>
    <script type="text/javascript">
    var str = '',
    data = [
    [
    { title : '第一章 表单常用代码'},
    { url : 'e/1/index.html', title : '去除字符串左右的空格' },
    { url : 'e/2/index.html', title : '验证用户是否输入' },
    { url : 'e/3/index.html', title : '禁止用户输入' },
    { url : 'e/4/index.html', title : '关闭用户中文输入法' },
    { url : 'e/5/index.html', title : '禁止用户复制和粘贴' },
    { url : 'e/6/index.html', title : '限制只能输入数字' },
    { url : 'e/7/index.html', title : '限制字符串长度' },
    { url : 'e/8/index.html', title : '仿微博提示可输入剩余字数' },
    { url : 'e/9/index.html', title : '换行文本自动滚动' },
    { url : 'e/10/index.html', title : 'Ctrl + Return提交表单' },
    { url : 'e/11/index.html', title : '文本内容进行关键字过滤' },
    { url : 'e/12/index.html', title : '全选反选少选复选框' },
    { url : 'e/13/index.html', title : '动态操作下拉选项' },
    { url : 'e/14/index.html', title : '级联菜单' },
    { url : 'e/15/index.html', title : '可添加的下拉选项' }
    ],
    [
    { title : '第二章 常用图片相关代码'},
    { url : 'e/16/index.html', title : '可添加的下拉选项' },
    { url : 'e/17/index.html', title : '图片放大镜效果' },
    { url : 'e/18/index.html', title : '点击图片逐渐放大' }
    ],
    [
    { title : '第三章 内容展示常用代码'},
    { url : 'e/19/index.html', title : '单元行上鼠标悬停提示' },
    { url : 'c/6/index.html', title : '无刷新切换皮肤，刷新后保存' },
    { url : 'e/20/index.html', title : '隔行换色鼠标经过换色' },
    { url : 'e/21/index.html', title : '添加或删除表格行' },
    //{ url : 'e/22/index.html', title : '表格的行拖动' },
    { url : 'c/1/index.html', title : '可拖动的弹出层' },
    { url : 'c/2/index.html', title : '选项卡轮播' },
    { url : 'c/3/index.html', title : '模拟滚动条' },
    { url : 'c/4/index.html', title : '缓动的对联广告' },
    { url : 'c/5/index.html', title : '拖动滑块验证' }
    ],
    [
    { title : '第四章 常用图片轮换'},
    { url : 'slide/01/index.html', title : '百度爱玩 - 图片轮换' },
    { url : 'slide/02/bd02.html', title : '百度爱玩 - 遮罩下拉' },
    { url : 'slide/03/bd03.html', title : '百度爱玩 - 榜单tab切换' },
    { url : 'slide/04/index.html', title : 'css3弹出层' },
    { url : 'slide/05/index.html', title : '米4-活动页面' },
    { url : 'slide/06/index.html', title : '百度爱玩 - 图片轮换' },
    { url : 'slide/07/index.html', title : '百度微购－中秋送好礼' },
    { url : 'slide/08/index.html', title : '商品分类' },
    { url : 'slide/10/index.html', title : '渐显的tab菜单2' },
    { url : 'slide/09/index.html', title : '经典图片轮换－单个滚动' },
    { url : 'slide/13/index.html', title : '经典图片轮换－整个翻页' }
    ],
    [
    { title : '第五章 移动端效果'},
    { url : 'm/01/index.html', title : '选项卡切换' }
    ],
    [
    { title : '第六章 时间日期效果'},
    { url : 'd/03/index.html', title : '全日历' },
    { url : 'd/04/index.html', title : 'canvas实现小时钟' }
    ],
    [
    { title : '第七章 其它练习'},
    { url : 'other/1/index.html', title : '乘法口诀输出' }
    ]
    ];
    for(var i = 0; i < data.length; i++){
    var items = data[i];
    var sub = '';
    for(var j=0; j<items.length; j++){
    var son = items[j];
    if(j == 0){
    sub += '<li><h1><a href="javascript:;" title="' + son.title + '">' + son.title + '</a></h1><dl class="sub-dl">';
    } else {
    sub += '<dd><a href="' + son.url + '" target="_blank" title="' + son.title + '">' + son.title + '</a></dd>';
    }
    if(j == items.length - 1){
    sub += '</dl></li>';
    }
    }
    str += sub;
    }
    var ol = document.getElementById('ol');
    ol.innerHTML = str;
    var h1 = ol.getElementsByTagName('h1');
    var dl = ol.getElementsByTagName('dl');
    var tmp = -1;
    var open = false;
    for(var i=0; i < h1.length; i++){
    h1[i].index = i;
    h1[i].onclick = function(){
    for(var i=0; i<h1.length; i++){
    dl[i].style.display = 'none';
    }
    if(tmp == this.index && open){
    dl[this.index].style.display = 'none';
    open = false;
    } else {
    dl[this.index].style.display = 'block';
    open = true;
    }
    tmp = this.index;
    }
    }
    
    </script>
    </body>
    </html>
