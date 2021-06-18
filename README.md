# test
```
 https://getcomposer.org/
 https://packagist.org/
 
 https://github.com/
```

# composer之创建自己的包
```
    ## 自定义你的 composer.json 包:
    ```
    官方文档 https://packagist.org/about#how-to-update-packages
    ```
    
    ## 将你的代码上传至gitHub后,且 发布一个releases 1.0.0版本(后台设置手动添加)
    
    ## 在packagist仓库中submit你的git项目；
    ```
    访问 https://packagist.org/packages/submit，
    将github项目地址: https://github.com/lifeofspring/test  复制在里面，然后 check 提交到 packagist中!
    
    之后就可以用 composer require lifeofspring/test
    若指定版本用 composer require lifeofspring/test v1.0.0
    
    特别注意，在你的git项目中 必须有你自定义项目的  composer.json 配置, 如:
     {
      "name": "lifeofspring/test",
      "type": "test",
      "description": "The test of lifeofspring.",
      "keywords": [
        "lifeofspring",
        "php"
      ],
      "homepage": "https://github.com/lifeofspring/test",
      "license": "MIT",
      "authors": [
        {
          "name": "",
          "email": "",
          "homepage": "http://xx.xx.xx",
          "role": "Developer"
        }
      ],
      "require": {
        "php": ">=7.0"
      },
      "autoload": {
        "psr-4": {
          "Lifeofspring\\Test\\": "src/"
        }
      }
    }
    ```
    
    ## 在GitHub中,配置和Packagist之间的自动更新钩子:
    ```
    首先，在 packagist 网站的设置中， Profile -> show API token 拿到你的 密钥，如 "xxxxe707ec23e194xxxx",
    其次，在 github 网站的设置中， Webhooks ->  Add webhook:
    Payload URl 填写你的地址，            如：  https://packagist.org/api/github?username=lifeofspring
    Content type 填写packagist提供的类型， 如:  application/json
    Secret 填写packagist提供的令牌,       如:   xxxxe707ec23e194xxxx
    内容类型： application/json
    秘密：您的Packagist API 令牌
    
    其他配置项，默认值即可,
    保存后，若配对成功，在 https://packagist.org/api/github (push) 前面 有个绿色小勾(即gitHub设置ok)
    
    在你的 packagist 网站对应项目中，会有个 绿色的 "This package is auto-updated." 提示
    ```
    
    ## 3. 测试GitHub 发布一个新 releases 版本 （需要登录网站后台,手动创建 -> Draft a new release), 看下你的 packagist的同步情况~
```

## 截止,你的自定义 composer