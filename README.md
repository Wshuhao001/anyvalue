anyvalue
========

高性能数据序列化库，可序列化为二进制，也可序列化为json，支持C++ java python php objectc 语言，兼容json数据格试，可以互相转换,可用于数据存储序列化，网序传输，远程调用，跨语言通信

php
========
###  安装
    修改Makefile,  
    PHP_EXT_HOME=php 扩展目录，供安装用
    PHP_SRC= php头文件目录
    执行sudo make & make install
###  使用    
    $obj['abc']='dasdasdsa';
    $obj['bcd']=10000;
    $obj['name']="sssssss";
    $obj['urls']=array('http://www.baidu.com','http://www.qq.com');
    $obj['info']['age']=19;
    $obj['info']['name']='helloworld';
    $obj['info']['price']=1.5555;

    $str = av_encode($obj);
    var_dump(av_decode($str));
    encode 比igbinary快2倍，decode性能相当

python
========
        import anyvalue
        obj=[1,2,3,4,-111,-1,-11111,1.5555,-1.11111,"dsadsdsdsads","dsdsadsadsds",{"a":1}]
        str = anyvalue.encode(obj)
        obj = anyvalue.decode(str)

c++
=========
### 使用
        c++只有一个头文件包含CAnyValue.h这个头文件即可
        CAnyValue oValue;
        oValue["abc"]=1;
        oValue["bcd"]="中国人helloaaa{}]\"'/\\*&^%$#@!><;:''''...,,中国人民大ddd";
        oValue["aa"].push_back("aaa{}]\"'/\\*&^%$#@!><;:''''...,,");
        oValue["aa"].push_back(-1001);
        oValue["aa"].push_back(-123);
        oValue["aa"].push_back(-123);
        oValue["aa"].push_back(ddwInt);
        oValue["aa"].push_back(CAnyValue());
        oValue["xbv"]["xx"]=1.51111111;
        oValue["xbv"]["xx2"] = -123455553234442444444444444444.111113334;
        oValue["xbv"]["ms"]="xxxx";
        oValue["xbv"]["xxxx"] =true;
        oValue["xbv"]["x"];
        string sBuf;
        oValue.encode(sBuf);
        CAnyValue oValue2;
        oValue2.decode(sBuf.data(),sBuf.size());
        uint32_t dwValue = oValue2["abc"].asUInt();

java
=========
        CAnyValue oValue = new CAnyValue();
        oValue.put("ABC");
        oValue.put(-100000000);
        oValue.put(-1);
        oValue.put(true);
        oValue.put(false);
        oValue.put(1.55555555);
        oValue.put(null);
        oValue.put(new CAnyValue());
        CAnyValue oValue1 = new CAnyValue();
        oValue1.put("name", "starjiang");
        oValue1.put("desc", "我爱北京天安门\n");
        oValue1.put("age", 30);
        oValue1.put("age2", 0);
        oValue.put(oValue1);
        oValue.put("starjiang\n");
        oValue.put("");
        String sBuf = oValue.encodeJSON();
        System.out.println(sBuf);
        byte[] sBuf2 = oValue.encode();
        CAnyValue oValue2 = new CAnyValue();
        oValue2.decode(sBuf2);
        String sBuf1 = oValue2.encodeJSON();
        System.out.println(sBuf1);
