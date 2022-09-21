# Distance-Evaluator
Java applet progam that evaluate the distance traveled at regular intervals of time, given the values of the initial velocity and the acceleration.
## The problem
The total distance travelled by a vehicle in t seconds is given by 
	Distance = ut + (at<sup>2</sup>)/2
Where u is the initial velocity (m/s), a is the acceleration (m/s<sup>2</sup>).
Write a java applet program to evaluate the distance traveled at regular intervals of time, given the values of u and a. The input and output should be on an option pane.
## The solution
### Java Code
```
import java.awt.*;
import java.awt.event.*;
import java.applet.*;
public class Assignment1b extends Applet implements ActionListener
{
	Label label1, label2, label3; TextField tf1, tf2, tf3;
	Button b1, b2, b3, b4;
	String whichButtonClk; //This String object will tell us which button is pressed
	public void init()
		{
		System.out.println( "Initializing an applet" );
		label1 = new Label( "Enter initial speeed u in m:" );
		tf1= new TextField( 10);
		label2 = new Label( "Enter acceleration a in ms^-2:" );
		tf2= new TextField( 10);
		b1 = new Button( "Distance" );
		add(label1);
		add(tf1);
		add(label2);
		add(tf2);
		add(b1);
		tf1.addActionListener( this); //Applet5 class registering to listen to first textfield event
		tf2.addActionListener( this); //Applet5 class registering to listen to second textfield event
		b1.addActionListener( this); //Applet5 class registering to listen to first button event
		}
	public void actionPerformed(ActionEvent ae)
		{
		if(ae.getActionCommand().equals( "Distance" ))// checking if an event of clicking the add/subtract/multiply/divide button is generated
			{
			whichButtonClk=ae.getActionCommand(); //initializing whichButtonClk to a String value of Button which is clicked
			repaint();
			}
		}
	public void paint(Graphics g)
	{
	g.drawString( "Please enter values of u and a to calculate distance" , 10, 130);
	if(tf1.getText().equals( "") && tf2.getText().equals("")) //if the add button is clicked when textfields are empty
		{}
	else
		{
		Integer i1= new Integer(tf1.getText());
		Integer i2= new Integer(tf2.getText());
		int timint[]= new int[5];
		timint[0]=2;
		timint[1]=4;
		timint[2]=6;
		timint[3]=8;
		timint[4]=10;
		for(int t=0; t<timint.length;t++){
		int distance = (i1*timint[t])+(int)(i2*Math.pow(timint[t],2)/2);
		if(whichButtonClk.equals( "Distance" ))
		g.drawString( "The distance at "+timint[t]+"s is " + distance +"m", 10, (50*t)+190);
		}
	}
	}
	}
```
### HTML Code
```
<html>
	<head>
		<title>Assignment_1b code</title>
	</head>
	<body>
		<applet code="Assignment1b.class" width="1000" height="500"></applet>
	</body>
</html>
```
## Compiled Codes
###### The following are all the codes plus the compiled class
