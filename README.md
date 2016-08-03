# Cordova-Plugin-Bluetooth-Printer
A cordova plugin for bluetooth printer for android platform, which support text printing and POS printing.

##Support
- Text
- POS Commands
- Image Printing (todo)
- Barcode Printing (todo)

##Install
Using the Cordova CLI and NPM, run:

```
cordova plugin add https://github.com/srehanuddin/Cordova-Plugin-Bluetooth-Printer.git
```



##Usage
Get list of paired bluetooth printers

```
BTPrinter.list(function(data){
        console.log("Success");
        console.log(data); \\list of printer in data array
    },function(err){
        console.log("Error");
        console.log(err);
    })
```


Connect printer

```
BTPrinter.connect(function(data){
	console.log("Success");
	console.log(data)
},function(err){
	console.log("Error");
	console.log(err)
}, "PrinterName")
```


Disconnect printer

```
BTPrinter.disconnect(function(data){
	console.log("Success");
	console.log(data)
},function(err){
	console.log("Error");
	console.log(err)
}, "PrinterName")
```


Disconnect printer

```
BTPrinter.disconnect(function(data){
	console.log("Success");
	console.log(data)
},function(err){
	console.log("Error");
	console.log(err)
})
```


Print simple string

```
BTPrinter.print((function(data){
    console.log("Success");
    console.log(data)
},function(err){
    console.log("Error");
    console.log(err)
}, "String to Print")
```

				{ 0x1b, 0x40 },// 0.复位打印机    
				{ 0x0A, 0x0A },// 1.打印并换行
    		
                { 0x1d, 0x21, 0x00 },// 2.字体不放大    
                { 0x1d, 0x21, 0x02 },// 3.宽高加倍    
                { 0x1d, 0x21, 0x11 },// 4.宽高加倍    

                {  0x1B, 0x61, 0 },// 5.左对齐
                {  0x1B, 0x61, 1 },// 6.居中对齐
                {  0x1B, 0x61, 2 },// 7.右对齐

                { 0x1b, 0x45, 0x00 },// 8.取消加粗模式
                { 0x1b, 0x45, 0x01 },// 9.选择加粗模式
Print simple printPOSCommand

```
BTPrinter.printPOSCommand(function(success){
}, function(error){
},"4") //写入对应数字，可以对字符进行调整
```