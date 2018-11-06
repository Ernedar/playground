#PLAYGROUND PROJECT STRUCTURE

Last update: `06. 11. 2018`

Author: Jarda 'Ernedar' Fišer

####1. Purpose
Whole Playground Project, or maybe even SCSS Framework someday need to be readable to another person than me and even with more files than 4 or 5 it will start to be unreadable. So this part is written for purpose of giving you some light on how is this project divided in to folders and what will you mostly find in different files.

####2. Folder structures
We will be using different types that SCSS provides for our playing. Mixins, Functions, Whole components, Support classes and in the first place Variables will have their own structure and their own bracket to put on.

If we take note on ATOM designing in CSS Styles:
- Variables are Protons and Electrons
- Functions are Atoms
- Mixins are Molecules no matter what size or number of lines in them
- Support Classes are molecular structures
- Components are your finalizes tools such as Navbar or Burger Menu Button

```
- COMPONENTS/
- FUNCTIONS/
- MIXINS/
- VARIABLES/
playground.scss
playground_comp_import.scss
style.scss
```

This is base folder and file import structure. 

File named `playground_comp_import.scss` is here for imports for encapsulated components, for example in Angular application. This file will consist of all needed functions, mixins and variable to use them inside those encapsulated components.

File named `playground.scss` will be used as import and comment file for all files in folders above it. Order of imports in this file is mandatory for correct functionality of whole ecosystem of Playground.

####3. File structure and Naming conventions

#####3.1 Playground File Naming Convention
If we put aside naming of two base files `playground.scss` and `playground_comp_import.scss` there is a system in this whole batch of files.

All files are done with `*.scss` extension that is to prevent code problems and incosistency, because `*.sass` extension for example do not know how to use logical operators that we can use in `*.scss` files.

All files that are part of Playground ecosystem will be written in lowercase and they will start with prefix `private_` just because all content in these files is not ment to be rewritten by users but used as it is to fasten your work and make it easier.

Next will be mark of what type of things you can find inside and in which folder it is stored:
- `var_` for variables
- `comp_` for components
- `mix_` for mixins
- `fnc_` for functions

And the postfix will be used for type of for example variables we will use the file. I case of colors it will be `private_var_color.scss` because they will be stored as variables. On the other hand if there will be some mixins for example for background color switching or background filters the file will be named `private_mix_color.scss`.

#####3.2 File Structure 
Inside each file the structure will be done to be atmost readable. I really hate archeology in code because it wastes time, so for example in functions the structure it will be like this:
```
// / FUNCTION NAME
// / @description Of the function you under these comments
// / @param $input-variable-if-needed {All | Types | That | Variable | Can  | Have} [default value if needed] - and description of the variable and where it is taken from.
// / @depencies On which is function dependant as $variables or @mixins
```
And after this description will be code of that function.

Variables will be with structure:
```
// / VARIABLE NAME
// / @description Of the variable and it is purpose
```

This structure is for future documentation purposes.

#####3.3 Specialized Files
There will be two more specialized files. These files will be even out of the Folder structure above. Files `playground_public_var_base.scss` and `playground_public_var_color.scss` will be used for you. In these files you can rewrite `!default` values of variables in `VARIABLES/private_var_base.scss` and base color settings in `VARIABLES/private_var_color.scss`. By these two files I would like to prevent errors and inconsistencies in whole system.

####4. System Import

How to import playground?
Simply write `@import 'playground';` to your `style.scss` file. And that is it.
If you want to import it to encapsulated component you need to make route for the play with component imports or use the hard file import with `/../../` structure.