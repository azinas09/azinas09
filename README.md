>>> import ipinfo
>>> from ipinfo.handler_utils import cache_key
>>>
>>> access_token = '123456789abc'
>>> handler = ipinfo.getHandler(access_token)
>>> ip_cache_key = cache_key('1.1.1.1')

# Check if IP is in the cache.
>>> ip_cache_key in handler.cache
True

# Get the IP's details from cache.
>>> handler.cache[ip_cache_key]
{'ip': '1.1.1.1', 'hostname': 'one.one.one.one', 'anycast': True, 'city': 'Miami', 'region': 'Florida', 'country': 'US', 'loc': '25.7867,-80.1800', 'org': 'AS13335 Cloudflare, Inc.', 'postal': '33132', 'timezone': 'America/New_York', 'country_name': 'United States', 'latitude': '25.7867', 'longitude': '-80.1800'}

# Set the IP's details to something else in the cache.
>>> handler.cache[ip_cache_key] = None

# Delete the IP from the cache.
>>> del handler.cache[ip_cache_key]
