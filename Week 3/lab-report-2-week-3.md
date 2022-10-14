# Week 3 Lab Report
## **Part 1: Simplest Search Engine**

**SearchEngine.java Code**

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.lang.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> wordList = new ArrayList<String>();
    String matches = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format(
                    "Welcome to the Search Engine!\nUse the 'add' path to add an string to the list and 'search' to query the list of strings");
        } else {
            if (url.getPath().contains("/add")) {

                String[] parameters = url.getQuery().split("=");

                if (parameters[0].equals("s")) {
                    wordList.add(parameters[1]);
                    return String.format("%s has been added to the list!", parameters[1]);
                }
            }
            if (url.getPath().contains("/search")) {
                System.out.println(wordList);
                String[] parameters = url.getQuery().split("=");
                ArrayList<String> matchStor = new ArrayList<String>();

                if (parameters[0].equals("s")) {
                    for (int i = 0; i < wordList.size(); i++) {
                        if (wordList.get(i).contains(parameters[1])) {
                            matchStor.add(wordList.get(i));
                        }
                    }
                }

                if (matchStor.size() > 0) {
                    return String.format("The search term matches the following strings in the list: %s",
                            matchStor.toString());
                } else {
                    return String.format("No strings matched '%s'", parameters[1]);
                }

            } else {
                return "404 Not Found!";
            }
        }

    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


---