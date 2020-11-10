# qrcode
生成二维码

## 开源地址
https://github.com/JZhao1020/qrcode

##1.安装
```
composer require hao/qrcode
```

##2.1 带logo二维码生成
```
// 远程图片
$url = 'http://xxx.com/images/2020/09/16013871254283.jpeg';

// 本地图片
$url = ROOT_PATH . 'public/image/logo.png';
$config = array(
    'ecc' => 'H',    // L-smallest, M, Q, H-best
    'size' => 12,    // 1-50
    'dest_file' => ROOT_PATH . 'public/image/qrcode2.png',
    'quality' => 90,
    'logo' => $url,
    'logo_size' => 100,
    'logo_outline_size' => 15,
    'logo_outline_color' => '#FFFFFF',
    'logo_radius' => 10,
    'logo_opacity' => 100,
);

// 二维码内容
$data = 'http://www.baidu.com';

// 创建二维码类
$oPHPQRCode = new \qrcode\PhpQrCode();

// 设定配置
$oPHPQRCode->set_config($config);

// 创建二维码
$qrcode = $oPHPQRCode->generate($data);
```

##2.2 不带logo二维码生成
```
$config = array(
    'ecc' => 'H',    // L-smallest, M, Q, H-best
    'size' => 12,    // 1-50
    'dest_file' => ROOT_PATH . 'public/image/qrcode2.png',
    'quality' => 90,
    'logo' => '',
    'logo_size' => null,
    'logo_outline_size' => null,
    'logo_outline_color' => '#FFFFFF',
    'logo_radius' => 100,
    'logo_opacity' => 0,
);

// 二维码内容
$data = 'http://www.baidu.com';

// 创建二维码类
$oPHPQRCode = new \qrcode\PhpQrCode();

// 设定配置
$oPHPQRCode->set_config($config);

// 创建二维码
$qrcode = $oPHPQRCode->generate($data);
```