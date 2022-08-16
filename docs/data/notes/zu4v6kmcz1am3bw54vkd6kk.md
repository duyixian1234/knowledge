
## 介绍

[playwright](https://pypi.org/project/playwright/)是一个 Python 浏览器自动化工具，支持不同操作系统下的多款浏览器。

|                        | Linux | macOS | Windows |
| :--------------------- | :---: | :---: | :-----: |
| Chromium 105.0.5195.19 |  ✅   |  ✅   |   ✅    |
| WebKit 16.0            |  ✅   |  ✅   |   ✅    |
| Firefox 103.0          |  ✅   |  ✅   |   ✅    |

## 使用

### 同步接口

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    for browser_type in [p.chromium, p.firefox, p.webkit]:
        browser = browser_type.launch()
        page = browser.new_page()
        page.goto('http://whatsmyuseragent.org/')
        page.screenshot(path=f'example-{browser_type.name}.png')
        browser.close()
```

### 异步接口

```python
import asyncio
from playwright.async_api import async_playwright

async def main():
    async with async_playwright() as p:
        for browser_type in [p.chromium, p.firefox, p.webkit]:
            browser = await browser_type.launch()
            page = await browser.new_page()
            await page.goto('http://whatsmyuseragent.org/')
            await page.screenshot(path=f'example-{browser_type.name}.png')
            await browser.close()

asyncio.run(main())
```
