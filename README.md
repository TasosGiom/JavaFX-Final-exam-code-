# JavaFX-Final-exam-code-
A javaFX exersice for school final exams with includes a 3d cube with a box-like base tha rotate with w and a keys 

package JavaFXApplication4.java;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.AmbientLight;
import javafx.scene.Camera;
import javafx.scene.Group;
import javafx.scene.PerspectiveCamera;
import javafx.scene.PointLight;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.effect.Effect;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.paint.PhongMaterial;
import javafx.scene.shape.Box;
import javafx.scene.shape.Rectangle;
import javafx.scene.transform.Translate;
import javafx.stage.Stage;


public class JavaFXApplication4 extends Application {
        final static int WINDOW_WIDTH = 1024;
    final static int WINDOW_HEIGHT = 720;
    @Override
    public void start(Stage primaryStage) {
       Box b = new Box(1400, 300, 1400);
         Box r = new Box();
       r.setWidth(200.0);
       r.setHeight(200.0);
       r.setDepth(200.0);
       PhongMaterial m = new PhongMaterial();
       m.setDiffuseColor(Color.RED);
       r.setMaterial(m);
       //Rectangle r = new Rectangle(100,100,Color.GREEN);
       r.setTranslateX(-50);
       r.setTranslateY(-50);
      
        //Group g = new Group(r);
        
        
        
        
        
        Group g = new Group(b, r);
         g.setTranslateX(WINDOW_WIDTH / 2);
        g.setTranslateY(WINDOW_HEIGHT / 2);
        Scene scn = new Scene(g, WINDOW_WIDTH, WINDOW_HEIGHT);
        Camera cam = new PerspectiveCamera();
        scn.setCamera(cam);
        scn.setFill(Color.DARKGRAY);
        primaryStage.setScene(scn);
        primaryStage.show();
        scn.setOnKeyPressed(event->{
        
            
       switch(event.getCode()){
       case A:
            r.translateXProperty()
           .set(r.getTranslateX()-10);
           r.setRotate(r.getRotate()-5);break;
       case D:
            r.translateXProperty()
            .set(r.getTranslateX()+10);
            r.setRotate(r.getRotate()+5 );break;
        
        }});
        
        scn.setCamera(cam);
       
        PointLight p = new PointLight();
        p.setColor(Color.YELLOW);
        p.getTransforms().add(new Translate(-50,-50,-50));
        scn.setFill(Color.DARKGRAY);
        primaryStage.setScene(scn);
        primaryStage.show();
          
         
        
    }

 
    public static void main(String[] args) {
        launch(args);
    }
    
}
