# Lab Report 2
---
# Part 1: StringServer
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
The 'handle' method from Server.java and the 'handleRequest' method from StringServer.java is called. The argument for the 'handle' method is a final type from the Httpexchnage class named 'exchange'. The argument for the 'handle' method is the URL which is the localhost link. The 'handle' value remains unchanged as 'handleRequests' takes the input before 'handle' does and handles it. The 'handleRequests' value changes as the URL is changed by the user and as shown above the gmail link was printed.
<img width="1440" alt="Screen Shot 2023-10-22 at 7 25 30 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/e182f581-7d18-4b67-b31e-4c280850a9e2">
The 'handle' method from Server.java and the 'handleRequest' method from StringServer.java is called. The argument for the 'handle' method is a final type from the Httpexchnage class named 'exchange'. The argument for the 'handle' method is the URL which is the localhost link. The 'handle' value remains unchanged as 'handleRequests' takes the input before 'handle' does and handles it. The 'handleRequests' value changes as the URL is changed by the user and as shown above added 'Prossefor Joe CSE 15L' right below the gmail link.

# Part 2: SSH Key
## Private Key
<img width="391" alt="Screenshot 2023-11-05 at 5 21 18 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/7690baf3-cede-4958-9431-9ba1ec6d5b59">


<br>

## Public Key
<img width="467" alt="Screenshot 2023-11-05 at 5 23 31 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/3fff875f-61fa-49d8-8482-7e322b0a83f1">


## Logging into ieng6 without password
<img width="666" alt="Screen Shot 2023-10-22 at 8 08 08 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/e41143aa-ba86-475f-933d-1b0ce2f5229d">


# Part 3: Reflection
In the lab for weeks 2 and 3, I learned the usage of ssh and the ability to access a computer or server, like the ieng6 server, remotely. Additionally, I learned how to create a ssh key in order to generate a key so I can log in to my ieng6 account without a password. This lab has also taught me how to resolve Java issues on Mac, especially when using the command javac, where I download JDK to resolve the issues.
