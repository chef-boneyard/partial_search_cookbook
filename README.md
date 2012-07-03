Description
===========

This cookbook provides the partial_search() method, which helps reduce bandwidth
consumption and speed up searches by allowing you to retrieve only part of a
search result (like just the IP address and name of a node, instead of the whole
node structure).

Usage
=====

Upload this cookbook and include it in the dependencies of any cookbook where
you would like to use the partial_search() method.

Example
=======

For example, instead of returning an entire, huge node structure, you might only
want the name and IP address.  To do this, you can run the following search:

    partial_search(:node, 'role:blah',
      :keys => { :name => [ 'name' ], :ipaddress => [ 'automatic', 'ipaddress' ] }
    ).each do |node|
      puts node['name']
      puts node['ipaddress']
    end
