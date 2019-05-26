# Spring Boot 线程池的使用和扩展

> 原文地址 http://blog.csdn.net/boling_cavalry/article/details/79120268

## 运行效果

![](https://raw.githubusercontent.com/gaohanghang/images/master/img20190526205613.png)

## 部分代码

```java
@Service
public class AsyncServiceImpl implements AsyncService {

    private static final Logger logger = LoggerFactory.getLogger(AsyncServiceImpl.class);

    @Override
    @Async("asyncServiceExecutor")
    public void executeAsync() {
        logger.info("start executeAsync");
        try{
            Thread.sleep(1000);
        }catch(Exception e){
            e.printStackTrace();
        }
        logger.info("end executeAsync");
    }
}
```