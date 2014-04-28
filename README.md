punto3
======
public class Akkatutorial {

 /**

 * @param args the command line arguments

 */

 public static void main(String[] args) {

 ActorSystem system=ActorSystem.create("Hola");

 ActorRef helloActor = system.actorOf(new Props(HelloActor.class), "que tal");

 helloActor.tell("que tal",null);

 helloActor2.tell("que tal",null);

 system.shutdown();

 system.awaitTermination();//JOIN

 }

}

class HelloActor extends UntypedActor{

 @Override

 public void onReceive(Object message) throws Exception {

 if(message instanceof String ) {

 String s=(String)message;

 switch (s){

 case "que tal":{

 System.out.println("");

 break;

 }

 default:

 System.out.println("huu?");

 }

 }

 else{

 unhandled(message);

 }

 }
