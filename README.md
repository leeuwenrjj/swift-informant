# OPENSTACK Informant - fork of swift-informat

Quick ugly hack:
Modified to use on general OpenStack services instead of just swift (some swift functions were removed)

Openstack Proxy Middleware to send events to a [statsd](http://github.com/etsy/statsd/ "statsd") instance.

**To utilize combined_events you'll need to run a statsd server that supports mulitple events per packet such as [statsdpy](https://github.com/pandemicsyn/statsdpyd)**

# Building packages

Clone the version you want and build the package with [stdeb](https://github.com/astraw/stdeb "stdeb"):

    git clone git@github.com:pandemicsyn/swift-informant.git informant-0.0.8
    cd informant-0.0.8
    git checkout 0.0.8
    python setup.py --command-packages=stdeb.command bdist_deb
    dpkg -i deb_dist/python-informant_0.0.8-1_all.deb

OR for centos

fpm -s python -t rpm setup.py
