# CountTime
<ul>
  <li>先计算出来每个星期二是当月的几号</li>
  <li>然后用endtime减去starttime得到差值</li>
  <li>利用差值计算倒计时</li>
</ul>



<h3>首先new Date() 当前年，月，日，星期几</h3>

  var week = time.getDay(); //获取星期几<br>
  var year = time.getFullYear(); //获取年份<br>
  var day = time.getDate(); //获取几号<br>
  var month = time.getMonth()+1; //获取月份<br>
  
  利用今天周几算下距离下个周二还有几天，把当前得到的几号加上距离的几天就是下个周二是本月的几号，但是在这里有个问题，
  假如说30号是周二，那下一个周二就是下个月的几号了，所以在这里我们要判断一下是否是过完本月，
  进而我们还要再判断一下本月有多少天
  
//判断是否是闰年
if(!(year%4)){//可以整除，是闰年
    //判断月份是30天还是31天
    if(month==1 || month==3 || month==5 || month==7 || month==8 || month==10 || month==12){
        fullday = 31;
    }else if(month==2){
        fullday = 29;
    }else{
        fullday = 30;
    }   
}else{//不可以整除，不是闰年
    //判断月份是30天还是31天
    if(month==1 || month==3 || month==5 || month==7 || month==8 || month==10 || month==12){
        fullday = 31;
    }else if(month==2){
        fullday = 28;
    }else{
        fullday = 30;
    }   
}
