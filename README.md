# How to create a Java application from scratch in Visual Studio Code

## Summary

This README gives a very quick step by step guide to creating a new, mostly empty, Java application in Visual Studio Code.  There are a few pre-requisites, not least of which is that Visual Studio Code and an appropriate JDK are installed.

These instructions might not be your best route to getting started with Java in Visual Studio code. Consider downloading and building a simple, known working, project first.

Following the instructions I'll provide some further tips that might help with troubleshooting if things don't go exactly as hoped for.

## Instructions

1. Start Visual Studio Code

1. Close any open files

1. Close the current folder (if open)

   ```File->Close Folder```

1. Open a new folder

   ```File->Open Folder...```

   Navigate to somewhere sensible, perhaps a folder where you can keep all your Java projects. Make a new folder if appropriate.

1. Right click in the ```Explorer``` view 

    Select ```Generate from Maven Archetype```

    You will be prompted to select a folder. Select the current folder.

1. You will be prompted to ```Select an archetype ...```

   Choose ```archetype-quickstart-jdk8```

1. The ```Maven``` terminal output window will show many ```[INFO]``` messages, ending with:

   ```
   [INFO] --- maven-archetype-plugin:3.0.1:generate (default-cli) @ standalone-pom ---
   [INFO] Generating project in Interactive mode
   [INFO] Archetype [com.github.ngeor:archetype-quickstart-jdk8:1.2.0] found in catalog remote
   Define value for property 'groupId':
   ```

   Your response to this and subsequent prompts should be something like this.

   ```
   Define value for property 'groupId': com.example.experiment.hello
   Define value for property 'artifactId': hello
   Define value for property 'version' 1.0-SNAPSHOT: :
   Define value for property 'package' com.example.experiment.hello: :
   ```
   You will then be prompted to confirm these are correct.

   ```
   Confirm properties configuration:
   groupId: com.example.experiment.hello
   artifactId: hello
   version: 1.0-SNAPSHOT
   package: com.example.experiment.hello
   Y: :
   ```

   Press return, or type ```N``` if you wish to be prompted to correct any of these.

   Note that the groupId, com.example.experiment.hello or similar, will typically be your package name.  Maven will now create the project folders, a sample app, and a pom.xml build file.

1. If all is well you should see the message ```[INFO] BUILD SUCCESS```

1. Now build your project!

## Pre-requisites

Visual Studio Code requires additional software to be installed before it can create and build Java projects.  See the tutorial.

https://code.visualstudio.com/docs/java/java-tutorial

## Troubleshooting

### Starting VSCode

My preference is to type the command ```code``` into the Git CMD console.

### No Internet connection (or slow connection)

The Maven build system is pretty much an Internet build system.  If you have no connection it is not going to work, or will be very tricky to configure.  You could consider using Ant instead.

If your connection is slow then you'll get a long pause after ```hello```
