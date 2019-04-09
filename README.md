### Instructions on how to set up Symfony

# 1.) I started by downloading Composer in order to get Symfony working.
# -One of the problems that came up with Composer was just simply getting started and figuring out the "command line PHP" I wanted to use at start-up.
# -The way I solved it, was reading and searching up information. The    directory that I choose is, C:\MAMP\bin\php\php7.2.8 for my php command line.

# 2.) I then opened up my command line and typed in "Composer" just to see all the commands it has.
# - From the commands, I choose "create-project". This is to create a new project in Composer. The full command is, "composer create-project"

# 3.) The symfony file I needed to download is called "website-skeleton" and the "json" can be found within github.
# - I realized that I did not download the right file; however, I did not notice since there isn't a big difference between "website-skeleton" and "symfony/skeleton".
# - I still downloaded symfony 4 and still managed to get the same results.
# - So now the command I wrote is, 'composer create-project "symfony/skeleton:4.0.0" '
# - The last thing to write in the command line, is a name for my project. Finalizing the command line as, "composer create-project 'symfony/skeleton:4.0.0' LabF".

# 4.) The file took a while, but it finally downloaded. One warning I received said, "Package symfony/lts is abandoned, you should avoid using it. Use symfony/flex instead." I did not figure out what it meant, but it was better than a warning.
# - The file ended with some configuring and it went through with not many problems.

# 5.) After the downloading finished, I decided to run the server through the command line.
# - exactly after the download stopped, I went to "php bin/console" to get a list of commands again.
# - Scrolling down, I found on how to run the server, which is "server: run"
# - The full command I wrote was, "php bin/console server:run"
# - The command "php bin/console server:run", did not work for me.

# 6.) I tried working on fixing running the server.
# - I thought that the problem was simply that I hadn't changed the directory to my project, so I changed the directory.
# - After changing the directory, I wrote "php bin/console server:run" again; however, it did not work and gave me a big red warning.
# - The warning I received said, "There are no commands defined in the "server" namespace."
# - For some reason I thought there was something wrong in my project directory, so the next command was "dir".
# - Then, I did some more research and wrote a command I found for my error is stackoverflow.com and wrote the command "composer require server --dev".

# 7.) That command worked for me, but once again I only got a warning that said, "Enable the "cURL" PHP extension for faster downloads". I did not know what command to fix that with.

# 8.) After the command, "composer require server --dev", it fetched some packages and did two installs.

# 9.) I decided to run the "php bin/console server:run" again, and it send an ok message saying, "[OK] Server listening on http://127.0.0.1:8001".
# - I went to the server and it said "Welcome to symfony" and that my application was ready and could start working on it.
# - Though, when I wrote out my directory, it just said there was no route found.

# 10.) I went back from the "ResourceNotFoundException" message and then I clicked where it said, "How to create your first page in Symfony", and followed along on the commands.

# 11.) I then opened my project with Atom, and went through information and videos on how to connect to the server with a route.

# 12.) The first thing the instructions said was to create a page name LuckyController, /lucky/number being the path.
# - The directory I put the file LuckyController, is under "src/Controller/LuckyController.php"
# - The page named LuckyController looks like so:

#      // src/Controller/LuckyController.php
#      namespace App\Controller;

#      use Symfony\Component\HttpFoundation\Response;

#      class LuckyController
#      {
#          public function number()
#          {
#              $number = random_int(0, 100);

#              return new Response(
#                  '<html><body>Lucky number: '.$number.'</body></html>'
#              );
#          }
#      }

# 13.) The first way it showed me to connect through a route was by going into "config/routes.yaml"
# - The code I wrote is:

#       app_lucky_number:
#       path: /lucky/number
#       controller: App\Controller\LuckyController::number

# 14.) This code did not work for me, the page kept giving me a "No Route Found" error again.
# - I could not get it working at all.
# I decided to try another way to connect to the route.

# 15.) I opened another terminal and changed my directory to my project.
# - Then, I wrote "php bin/console" to see the commands once again.

# 16.) I wrote down the "debug:router command". There were no names or paths.
# - So, I decided to continue with the instructions and wrote "composer require annotations".
# - I waited for everything to download and it prefetched seven packages and did eight installs.

# 17.) After the configuration and installing finished with the annotations, I wrote the following command "php bin/console debug:router", but nothing showed up.
# - I went back to Atom and changed the LuckyController file by simply adding:

#     "use Symfony\Component\Routing\Annotation\Route;"

# and  then added:

#     /**
#      * @Route("/lucky/number")
#     /

# 18.) Then for the file "routes.yaml", commented everything out.

# 19.) I went back to my terminal and wrote "php bin/console debug:router" and received the name: app_lucky_number and the path: /lucky/number

###This is all of the documentation and the end for my symfony project.
