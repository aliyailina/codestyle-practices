# Useful TODOs

- ***`_NOTE:`*** \
    Mark something, that will need your attention during refactor. It is not necessary something that you *must* change during refactor, rather something, that *can* be changed.
    > *You develop a page that contains collection of items. You can manipulate items such as delete, add, etc. Suppose, you have a situation when user can't remove item from collection (f.e. your collection is associated with server and there is no internet on user device). In that case you need to make user know that he can't delete this item. You can do it two way (or maybe more): send user and alert at the bottom of the screen or show him a dialog that he can close by clicking on a button. And you don't know which is better. So you can realise one of the way (f.e. by dialogs) and make a **`_NOTE`** todo like this:*
    
***`_NOTE: maybe some dialogs (like "Cannot remove <item>) can be replaced with alerts`***

***`_NOTE`*** it is something very like default TODO, but it is more precise (especially when you mix up it with other TODO's).
  
#
  
- ***`_BRANCH_NOTE [<branch_name> / <task number>]:`*** \
    This note is for developers who develops features on separate branches, and only after feature complete merge/rebase this branch into main branch. This is the same as ***`_NOTE`*** todo, but if ***`_NOTE`*** todo must be removed after refactor, ***`_BRANCH_NOTE`*** todo must be removed before merging/rebasing branch with your feature into develop. So, ***there must be no ***`_BRANCH_NOTE`*** todo's in your main branch.***

    > *You develop something on separate branch with name `1234-my-feature`, f.e. method, that use method JamesMethod() created by another developer James in your team. And you need another modification of this method for your feature (f.e. you need it returns AnotherType instead of CurrentType that it returns now). So, you ask your teammate to create this modification and notify you when it will be completed. And, to not forget, you should create **`_BRANCH_NOTE`** todo like this:* 

    ***`_BRANCH_NOTE [1234]: wait for update JamesMethod() by James. It must return AnotherType instead of CurrentType.`*** 

    Also, you should specify branch identifier inside ***`_BRANCH_NOTE`*** todo for one reason: we all make mistakes, so it can be situation when you merge/rebase your feature branch into main and forget to clean some ***`_BRANCH_NOTE`*** todo('s). Later, when you have see it, you will know that it should be removed as soon as possible and it is not supposed to be in your main branch. 

#


- ***`_BUG:`*** \
        Does it need an explanation? Todo for bugs. \
        ***`_BUG: swipe inside collection's item doesn't work.`*** 

#

- ***`_HOTFIX:`*** \
    This todo is for situations, when you need to complete feature (fix bug) as soon as possible, and you have no time for clean, good and tasty code. Write your smelling code and notice it with ***`_HOTFIX:`*** todo. And, for God's sake, describe it. Don't just write "***`_HOTFIX:`***" with no description. If you do it, it is good practice to FIRE YOU. 

    > *Suppose you have a collection and customer want you to realise searching and filtering through this collection today. Of course, you have no time to think "Oh, maybe some interesting, complicated and unintelligible lib in the internet and I can waste two weeks to study it" or "Oh, where is my dry-erase board, I would write the architecture that would explode minds". But you have time to write the code of "it works it's enough"-type. So, you can write it and mark using **`_HOTFIX:`** todo*

    ***`_HOTFIX: This is a filter for collection, but it is quick-and-dirty. The idea is <describe your idea or give a reference when other developers can find it>.`*** 

#

- ***`_?:`*** \
    This todo is to make other developers know that their code is very interesting and concept-arted. So interesting, that you waste a lot of time to read and understand what the author meant. Shorter, code need to be explained or refactored by another developer (or maybe by you, but later).

    > *You read the code and see class like this (this is pseudo-C#):*

    ```csharp
    class X: I1, I2, IInterfaceWithNameThatHasNoSense, II
    {
    	protected WTFType _iAmVariableThatShouldBePrivateButWhoCaresAboutModifiers;
    	public WTFType2 _ahahahahahYouHasTrickedLol;
    	public int OKITLOOKSLIKEJOKEBUTIREALLYSAWTHEVARRIABLESTHATUSETHISCASE = (Type1)(Type2)(Type3)_nooneKnowWhyINeedSoManyCasts;

    	public internal async void Method1()
    	{
    		/*
    			commented code here
    		*/
    	}

    	protected internal I1.iAmThePropertyThatDoNothingButWhoCares { get; set; }
    	
    	public bool Method2()
    	{
    		/*
    			commented code here
    		*/
    		bool iAmTheBoolValue;
    		if(someExpression)
    		{
    			return true;
    		}
    		else
    		{
    			return false;
    		}

    		int i = 0;
    	}
    }
    ```

    This is exactly the place for ***`_?:`*** todo. And, of course, this todo is only for developing. Don't release you code with ***`_?:`*** todo. Of course, you can add any text to make the developer know that you was very interested by this code. Something like:

    ***`_?: Haha, nice joke man`***

    or

    ***`_?: All team have been trying to understand what is happening here. We can't. Can you explain?`***
 
#

- ***`_COMMENTED_CODE:`***
    
    This is todo that you should never ever use. Never. Because you should never ever have commented code. But, you know, it is like push --force — if there is nobody who can see it... Ok, it can be situations, when you need to comment some code to disable some features during developing. And this todo is for situations like this. But, remember: you must delete all commented code before pushing your changes to main branch. Be clean.

    > You have some, f.e., class in your project, and you need to rewrite it. In this situation you need to make old class invisible for all program, but visible for you — to have the base for rewriting. In this case it would be nice to comment your old realization and you can (and you should) mark it using ***`_COMMENTED_CODE`*** todo.

    ***`_COMMENTED_CODE: new realization is in develop, use this class as base for newer.`***

    But you should remember: ***you must clean all of your commented code before pushing to main branch.***. And I highly recommend you to write description for your commented code for the same reason as for ***`_BRANCH_NOTE`*** todo: we all make mistakes, so it can be situation when you push your commented code to main branch, and see it after a long time. And if you describe it, you will exactly know why it is here, and maybe there is something that you (or other developers) missed. 
    
 #

Of course, all this TODO's is almost useless, if you doesn't implement it as TODO's in your IDE -- in that case this is just a comments. So mix the power of TODO's with power of your IDE (you can ever use the power of your compiler and do the warnings and errors based on this todo's). \
If you want to say that author is an idiot (or maybe you have some remarks), you can contact me through the Telegram: https://t.me/psevdointellektuall. \
Be aware writing your code! 
