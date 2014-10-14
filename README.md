registry.butts
==============

the 100% legit official .butts domain name registry

## how do i register my own .butts domain?
send a pull request adding a file with the domain name you want, e.g., `revolution.butts` in the `/domains/` folder.

the contents of the file should be valid JSON describing DNS records, like such: 
```json
{
  "@a": ["104.131.66.225"],
  "www": {
    "@cname": ["jden.butts."]
  }
}
```

## how much does my .butts domain cost?
It's absolutely free. Think about it - it's just a minuscule entry in some computer
database somewhere. Why on earth should there be a fee associated with that?
For that matter, I'm not sure why any other domain registrar charges, either.

## go on, gimme details

I'll get around to documenting the file format more later, but for now
feel free to ask in the issues or in your pull request and we will help
make sure it's right!

Essentially, starting at your second level domain, eg `foo.butts`, you
can create records or subdomains in the json tree. Records start with '@',
and subdomains are any other json property. This way, the tree structure of
the json document matches the subdomain structure.

We also support cnames at second level domains - no need to mess around
with "alias" records like some other dns registries or services. We just
Do The Right Thing^TM.


The part in the "name" property is the subdomain - use "@" for the raw domain, and "*" for a wildcard subdomain.

The start of authority is the domain name in the file name - in this case whatever.butts.

## how do I use .butts domains

This requires a dns proxy.

Currently, there is an experimental .butts-compliant DNS server running at `104.131.66.225` - uptime not guaranteed.

You can also [run your own](https://www.npmjs.org/package/dotbutts) which is better for your privacy since it means your DNS requests never go to the .butts server.

## contact

come say hi in [#dotbutts on irc.freenode.net](https://webchat.freenode.net/?channels=dotbutts)

## code of conduct
.butts has values, see https://github.com/jden/registry.butts/blob/master/CONTRIBUTING.md -
essentially, we won't let you register a stupid domain, and if you're doing things that are bad and hurting people we will delete your .butts domain so fast you won't realize what happened to your .butts, so be nice.
