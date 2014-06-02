Bundle-Gem
==========

##*ADA* Application Answers to Question 3 

###Reading Assessment###


   1. Q: What does the command **bundle gem foodie** do?<br>
   A: **bundle gem foodie** creates a gem using Bundler. **foodie** is used in order to portray the gem, for example as "Delicious!" or "Gross!"

   2. Q: In what folder do we put our test files?<br>
   A: Test files go in a **spec** directory at the root of the gem by using the command: *mkdir spec*

   3. Q What do we need to write to add the **activesupport (version 4.0.0)** dependency to our gemspec?<br>
   A: To specify the dependency on the **activesupport (version 4.0.0)** add this link inside ***Gem::Specification*** object: ***spec.add_dependency "activesupport", "~>4.0.0"***

   4. Q: What steps need to be taken to write a generator?<br>
      * Steps:<br>
	        1. Define generator class:<br>
			
		----
	        desc "recipe", "Generates a recipe scaffold"
            def recipe(group, name)
            Foodie::Generators::Recipe.start([group, name])
            end</br>
			
		----
		 <br>2. Require a file for the new class:
		 
		 ----
		    require 'foodie/generators/recipe'</br>
			
		----
		 <br>3. Define this class, inherit from Thor::Group, include Thor::Actions, name the location "geneators": **lib/foodie/generators/recipe.rb**<br>
		 **require 'thor/group'**

		 ----
		 module Foodie<br>
			module Generators<br>
				class Recipe < Thor::Group<br>
					include Thor::Actions<br>

					argument :group, :type => :string
					argument :name, :type => :string
					end
				end
				
		----
		 <br>4. Make generator generate by defind methods in class. Define a *create_group* method inside this class which will create a directory.
		 
		 ----
		  def create_group
			 empty_directory(group)
		   end
		   
		 ----
		   
		 
		    
		 
		 
