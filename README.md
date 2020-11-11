# Java-Project
public class FileReader {

    /**
     * @param args the command line arguments
     */
    static String name, status, surname, gender, title;
    static int age;
    static boolean chec = true;
    public static void main(String[] args) throws FileNotFoundException{
         //creating File instance to reference text file in Java
        File text = new File("C:/Users/lsant/Desktop/JavaProjects/SAMPLE FILES FOR CA 1-20201109/people2.txt");
     
        //Creating Scanner instnace to read File in Java
        Scanner scnr = new Scanner(text);
        do{
        int lineNumber = 1;
          for(int i=1; i<=3;i++){
            if(lineNumber==1){
             name = scnr.nextLine();  
            }else if(lineNumber==2){
              age = Integer.parseInt(scnr.nextLine());  
            }else if(lineNumber==3){
             gender = scnr.nextLine();   
            }
            
            lineNumber++;
        }  
        
       if(gender.equals("M")){
         title = "Mr.";
       }else if(gender.equals("F")){
         title = "Ms."; 
       }else if(gender.equals("T")){
         title = "Mx.";  
       }else if(!gender.equals("M") || !gender.equals("F")|| !gender.equals("T") ){
          System.out.println("ERROR: Incorrect gender");
          System.exit(0); 
       }
       if(age<=18){
           status="School";
       }else if(age>=19 && age<=25){
           status="College";  
       }else if(age>=26 && age<=66){
           status="Worker";
       }else if(age >=67 && age <=100){
           status="Retired";  
       }else if(age>100){
          System.out.println("ERROR: THe age cannot be above 100");
          System.exit(0);
       }
       System.out.println(title+""+name+"\n"+status);
    }
        while(scnr.hasNextLine());{
    
}
    
    }
}
