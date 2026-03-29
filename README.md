# tweety
Reverse Engineered Twitter Frontend API.

[![Downloads](https://static.pepy.tech/personalized-badge/tweety-changchiyou?period=total&units=international_system&left_color=orange&right_color=blue&left_text=Downloads)](https://pepy.tech/project/tweety-changchiyou) [![PyPI](https://img.shields.io/pypi/v/tweety-changchiyou)](https://pypi.org/project/tweety-changchiyou/)

## Installation:
```bash
pip install tweety-changchiyou
```

## Keep synced with latest fixes

```bash
pip install https://github.com/changchiyou/tweety/archive/main.zip --upgrade
```

## A Quick Example:
```python
    from tweety import TwitterAsync
    import asyncio
    
    async def main():
    
        app = TwitterAsync("session")  
        all_tweets = await app.get_tweets("elonmusk")
        for tweet in all_tweets:
            print(tweet)

    asyncio.run(main())
```

> [!IMPORTANT] 
> Even Twitter Web Client has a lot of rate limits now, Abusing tweety can lead to `read_only` Twitter account.

Do check [FAQs](https://github.com/changchiyou/tweety/wiki/FAQs)

Full Documentation and Changelogs are [here](https://mahrtayyab.github.io/tweety_docs/)

## Fork Information

This is a fork maintained by [changchiyou](https://github.com/changchiyou). Original project by [mahrtayyab](https://github.com/mahrtayyab/tweety).
