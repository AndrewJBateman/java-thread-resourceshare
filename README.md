# :zap: Java Thread Resource Share
 
* Java code for a Java Programming Masterclass Section 15-282 Concurrency in Java- see [:clap: Inspiration](#clap-inspiration) below
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/java-thread-resourceshare?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/java-thread-resourceshare?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/java-thread-resourceshare?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/java-thread-resourceshare?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Java Thread Resourceshare](#zap-java-thread-resourceshare)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:file_folder: License](#file_folder-license)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* [class Interface Lock](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/locks/Lock.html) used for controlling access to a shared resource by multiple threads.

## :camera: Screenshots

N/A

## :signal_strength: Technologies

* [Java v11](https://www.java.com/en/)

## :floppy_disk: Setup

* Open folder in an IDE such as IntelliJ. Run  from `Main.java`

## :computer: Code Examples

* `Main.java` main function showing 2 worker functions sharing the same resource

```java
public class Main {

  public static void main(String[] args) {
    final Worker worker1 = new Worker("Worker 1", true);
    final Worker worker2 = new Worker("Worker 2", true);
    final SharedResource sharedResource = new SharedResource(worker1);

    new Thread(new Runnable() {
      @Override
      public void run() {
        worker1.work(sharedResource, worker2);
      }
    }).start();

    new Thread(new Runnable() {
      @Override
      public void run() {
        worker2.work(sharedResource, worker1);
      }
    }).start();
  }
}
```

## :cool: Features

* N/A

## :clipboard: Status & To-Do List

* Status: Working.
* To-Do: Nothing

## :clap: Inspiration

* [Udemy: Java Programming Masterclass for Software Developers](https://www.udemy.com/course/java-the-complete-java-developer-course/learn/lecture/3561816#overview)

## :file_folder: License

* N/A

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org), email: gomezbateman@yahoo.com
