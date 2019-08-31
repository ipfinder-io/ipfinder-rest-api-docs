# Libraries
## Language Libraries

Official libraries for common programming languages, like PHP, Python etc.


| Language   | Status       | Link         | Package Manager|
| ---------- | ------------ | ------------ | ------------   |
| Javascript | Released |[ipfinder-io/ip-finder-node](https://github.com/ipfinder-io/ip-finder-node)|[ipfinder](https://www.npmjs.com/package/ipfinder)|       
| Java       | Released  |[ipfinder-io/ip-finder-java](https://github.com/ipfinder-io/ip-finder-java) |[ipfinder-io](https://search.maven.org/search?q=a:ipfinder-io)|
| Python     | Released |[ipfinder-io/ip-finder-python](https://github.com/ipfinder-io/ip-finder-python)|[ipfinder-io](https://pypi.org/project/ipfinder-io/)|                 
| PHP        | Released |[ipfinder-io/ip-finder-php](https://github.com/ipfinder-io/ip-finder-php)|[ipfinder/ipfinder](https://packagist.org/packages/ipfinder/ipfinder)|                            
| Ruby       | Released |[ipfinder-io/ip-finder-ruby](https://github.com/ipfinder-io/ip-finder-ruby)|[Ipfinder](https://rubygems.org/gems/Ipfinder)|  
| R          | Released  |[ipfinder-io/ip-finder-rlang](https://github.com/ipfinder-io/ip-finder-rlang) ||
| Perl       | Released  |[ipfinder-io/ip-finder-perl](https://github.com/ipfinder-io/ip-finder-perl) ||
| D          | Released  |[ipfinder-io/ip-finder-dlag](https://github.com/ipfinder-io/ip-finder-dlang) |[ipfinder](https://code.dlang.org/packages/ipfinder)|  
| Lua        | Released  |[ipfinder-io/ip-finder-lua](https://github.com/ipfinder-io/ip-finder-lua) |[ipfinder](https://luarocks.org/modules/benemohamed/ipfinder)|  
| elixir     | Released  |[ipfinder-io/ip-finder-rlang](https://github.com/ipfinder-io/ip-finder-elixir) |[ipfinder](https://hex.pm/packages/ipfinder)|
| Go         | In progress  | ||
| C#         | In progress  | ||
| Rust       | In progress  | ||
| Haskell    | In progress  | ||
| Erlang     | In progress  | ||
| C          | In progress  | ||


## Framework Libraries

Official libraries for common frameworks. These libraries should use the official lanaguge library as a dependency, so for example the Django library should use the Python library.

In the framework libraries we can assume more about the developer's use case, and we probably have access to more information, such as a HTTP request object. We can therefore implement additional functionality that
doesn't make sense in the core language library. This includes bot filtering (not sending requests to our API if the user agent belongs to a "bot").

The framework libraries should make it *as simple as possible* to use our API. For example, ideally only a few lines of code would be required to get ipfinder data for everyone accessing your Ruby site.

| Framework                      | Status      | Link                                              
| ------------------------------ | ----------- | ------------------------------------------------- 
| Express  (NodeJS - Javascript) | In progress |                                                   |
| Meteor (NodeJS - Javascript)   | Released    |[ipfinder-io/ip-finder-meteor](https://github.com/ipfinder-io/ip-finder-meteor)| 
| Spring  (Java)                 | In progress |                                                   | 
| Laravel (PHP)                  | In progress |                                                   | 
| CodeIgniter (PHP)              | Released    |[ipfinder-io/codeigniter-ipfinder](https://github.com/ipfinder-io/codeigniter-ipfinder)|
| cakephp (PHP)                  | Released    |[ipfinder-io/cakephp-ipfinder](https://github.com/ipfinder-io/cakephp-ipfinder)|
| Django (Python)                | In progress |                                                   | 
| Rails (Ruby)                   | In progress |                                                   | 

## Third party libraries
There are a large number of unofficial ipfinder libraries written by third parties. While these aren't maintained by us and haven't been tested by us these libraries can be a great way to get started quickly with ipfinder if you're using a language or framework that we don't have an official library for. Search GitHub for [ipfinder](https://github.com/search?q=ipfinder) libraries.


If you’ve written a ipfinder library and would like to add it to this page, send an email to info@ipfinder.io.
