# 快速上手TEngine

## 1.创建空场景并创建TEngine（GameObject）
![图片](/images/快速开始-Scene.png)

## 2.创建游戏入口脚本继承TEngine

创建主入口脚本Test,继承TEngine的入口基类，挂载到场景的TEngine（GameObject）即可
```csharp{1,5}
public class Test : TEngine.TEngine
{
    protected override void RegisterAllSystem()
    {
        base.RegisterAllSystem();
        AddLogicSys(UISys.Instance);
    }

    protected override void StartGame()
    {
        TimerMgr.Instance.AddTimer(
            (_) =>
            {
                Debug.LogError("timer tick!");
            },
            0.5f,
            true
        );

        //TODO ....
    }
}
```
## 3.TEngine 运行成功！
![图片](/images/快速开始-Result.png)
