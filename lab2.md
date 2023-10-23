# Lab Report 2
---
## Part 1: StringServer
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> mess = new ArrayList<String> ();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Welcome!");
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    mess.add(parameters[1]);
                    String result = "";
                    for (int i = 0; i < mess.size(); i++) {
                        result = result + mess.get(i) +"\n";
                    }
                    return String.format("%s", result);
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
```
<img width="1436" alt="Screen Shot 2023-10-22 at 7 25 19 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/8a6ba53f-ecc9-4ec6-8933-6f3695b2c13b">
In the screenshot above, the add-message query method is being called with a URI value from gmail.com. The method proceeded to add the code into the String array named mess and was able to handle a value of a URI.
<img width="1440" alt="Screen Shot 2023-10-22 at 7 25 30 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/e182f581-7d18-4b67-b31e-4c280850a9e2">
In the screenshot above, the add-message query method is being called with a value of "Professor Joe CSE 15L. The method proceeded to add the code into the String array named mess and was able to handle a value with spaces, numbers, and characters. 
The method also printed the next value onto a new line allowing for the two values to stack.

# Part 2: SSH Key

