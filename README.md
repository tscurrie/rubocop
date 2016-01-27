# RuboCop Gem Demonstration

[RuboCop GitHub documentation link](https://github.com/bbatsov/rubocop)

RuboCop is a Ruby static code analyzer. It will enforce many of the guidelines out lined in the community [Ruby Style Guide.](https://github.com/bbatsov/ruby-style-guide) Apart from reporting problems in your code, RuboCop can also automatically fix some of the problems for you. 


##### Installation:

Type this code in your project directory,
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
*rubocop -h* | help
*rubocop -L* | List of all files rubocop will inspect
*rubocop -F* | this will inspect to the first error allowing you to fix your code one error at a time
*rubocop -D* | Displays cop names in offense messages
*rubocop -C* | Run wit specified config file
*rubocop -l* | Run only lint cops
*rubocop -a* | Auto correct certain offense Note: Experimental
*rubocop --only* | Run only specified cops 
*rubocop --except* | Run all cops except specified

#### Problems I ran into

I had a number of problems disabling cops/checks. To get this to work, youre going to first run 
```sh
rubocop --auto-gen-config 
```
This will generate the file *rubocop_todo.yml* in your repository. This file shows all the major errors that you have in your project. To disable and modify cops you will then need to create the root file 
```sh
.rubocop.yml
``` 

You then have to include the line,
```sh
 inherit_from: .rubocop_todo.yml
```
at the top. At this point you can start to disable cops. 

This [website](https://docs.chef.io/rubocop.html) was very helpful. it states that the general syntax for disabling/modifying cops is:
```sh
Syntax¶
A .rubocop.yml file has the following syntax:

NAME_OF_RULE:
  Description: 'a description of a rule'
  Enabled : (true or false)
  KEY: VALUE
where

NAME_OF_RULE is the name of a rule
Description is the string that prints as part of the standard output that describes the rule if it is triggered during the evaluation
Enabled enables a rule (true) or disables a rule (false); for non-custom rules, this value will override the settings in the enabled.yml and disabled.yml files in RuboCop
KEY: VALUE adds additional details for a rule, if necessary. For example, Max: 200 sets the line length to 200 characters for the LineLength rule
```

A cop that is really annoying is the *Line is too long error*, you will see this a lot. To alter that error you could copy and paste this code to your *.rubocop.yml*.

```sh
Metrics/LineLength:
  Max: 99
```
Or to disable this cop completely

```sh
Metrics/LineLength:
  Enabled: false
```
