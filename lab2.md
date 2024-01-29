# Lab Report 2

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> chat = new ArrayList<>();
    String userMessage;
    String user;
        public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Chat Time!");
        } 
        else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            String[] split = parameters[1].split("&");
                if(parameters[0].equals("s")) {
                    userMessage = split[0];
                }
                if(split[1].equals("user")) {
                    user = parameters[2];
                }
                chat.add(String.format("%s: %s", user, userMessage));
                String chatBlock = chat.get(0) + "\n";
                //Concatenate a string for every element in the ArrayList
                for(int i = 1; i < chat.size(); i++) {
                    chatBlock += chat.get(i);
                    chatBlock += "\n";
                }
                return chatBlock;
        }
        return "404 Not Found!";
    }
    
}

class Message {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

![Image](ChatExample1.png)
![Image](ChatExample2.png)
![Image](NoPassword.png)
![Image](PublicKeyPath.png)
![Image](PrivateKeyPath.png)


