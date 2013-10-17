This puppet module skeleton is based on stdmod naming standards.

It provides:
 - a basic package/service/configration main class
 - a general purpose conf define
 - puppet-lint, rspec, rspec-system tests

The skeleton is based on these excellent works:

https://github.com/garethr/puppet-module-skeleton

https://github.com/spiette/puppet-module-skeleton


## Installation

As a feature, puppet module tool will use ~/.puppet/var/puppet-module/skeleton
as template for its `generate` command. The files provided here are
meant to be better templates for use with the puppet module tool.

As we don't want to have our .git files and this README in our skeleton, we export it like this:

    git clone https://github.com/stdmod/puppet-module-skeleton
    cd puppet-module-skeleton
    rsync -av --delete --exclude '.git' .  $HOME/.puppet/var/puppet-module/

## Usage

The just generate your new module structure like so:

    puppet module generate user-module

Once you have your module then install the development dependencies:

    cd user-module
    bundle install

Now you should have a bunch of rake commands to help with your module
development:

    bundle exec rake -T
    rake build             # Build puppet module package
    rake clean             # Clean a built module package
    rake coverage          # Generate code coverage information
    rake help              # Display the list of available rake tasks
    rake lint              # Check puppet manifests with puppet-lint / Run puppet-lint
    rake spec              # Run spec tests in a clean fixtures directory
    rake spec:system       # Run system tests
    rake spec_clean        # Clean up the fixtures directory
    rake spec_prep         # Create the fixtures directory
    rake spec_standalone   # Run spec tests on an existing fixtures directory
    rake spec_system       # Run RSpec code examples
    rake syntax            # Syntax check Puppet manifests and templates
    rake syntax:manifests  # Syntax check Puppet manifests
    rake syntax:templates  # Syntax check Puppet templates

Of particular interst should be:

* `rake spec` - run unit tests
* `rake spec:system` - run full system tests (requires vagrant)
* `rake lint` - checks against the puppet style guide
* `rake syntax` - to check your have valid puppet and erb syntax

