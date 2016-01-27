# RuboCop Gem Demonstration

[GitHub documentation link](https://github.com/bbatsov/rubocop)

RuboCop is a Ruby static code analyzer. It will enforce many of the guidelines out lined in the community Ruby Style Guide. Apart from reporting problems in your code, RuboCop can also automatically fix some of the problem for you. 

#### Prerequisites:

##### Installation:

Type 
```sh 
$ gem install rubocop
```

running *Rubocop* with no arguments will check all Ruby source files in current directory.

To pass specific files use
```sh
$ rubocop app spec lib/something.rb
```

### Commands that I found most helpful:

Command | Description
--- | ---
*rubocop - h* | help
*rubocop - L* | List of all files rubocop will inspect
*rubocop - F* | tis will inspect to the first error allowing you to fix your code one error at a time
*rubocop - D* | Displays cop names in offense messages
*rubocop - C* | Run wit specified config file
*rubocop - l* | Run only lint cops
*rubocop - a* | Auto correct certain offense Note: Experimental
*rubocop --only* | Run only specified cops 
*rubocop --except* | Run all cops except specified

