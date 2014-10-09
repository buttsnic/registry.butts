registry.butts
==============

the 100% legit official .butts domain name registry

## how do i register my own .butts domain?
send a pull request adding a file with the domain name you want, e.g., `revolution.butts` in the `/domains/` folder.

the contents of the file should be valid JSON describing DNS records, like such: 
```json
{
    "ns": [
        { "host": "NS1.NAMESERVER.BUTTS." },
        { "host": "NS2.NAMESERVER.BUTTS." }
    ],
    "a": [
        { "name": "@", "ip": "127.0.0.1" },
        { "name": "www", "ip": "127.0.0.1" },
        { "name": "mail", "ip": "127.0.0.1" }
    ],
    "aaaa": [
        { "ip": "::1" },
        { "name": "mail", "ip": "2001:db8::1" }
    ],
    "cname":[
        { "name": "mail1", "alias": "mail" },
        { "name": "mail2", "alias": "mail" }
    ],
    "mx":[
        { "preference": 0, "host": "mail1" },
        { "preference": 10, "host": "mail2" }
    ]
}
```

The part in the "name" property is the subdomain - use "@" for the raw domain, and "*" for a wildcard subdomain.
The start of authority is the domain name in the file name - in this case whatever.butts.

## how do I use .butts domains

This requires a dns proxy. You can [run your own](https://www.npmjs.org/package/dotbutts). There is not yet a publically
available dns proxy for .butts, but if you want to start one, let me know and I'll link it here.
