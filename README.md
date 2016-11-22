# Portfolio
-----------

##CSharp


###Oefeningen uit het handboek 
  
- Oplossing oef 5.9


```C#
using System;

public class Program
	{

	private static double KubusVolume(double r) {
		double vol = r * r * r;
		Console.WriteLine("Gegeven is straal {0}", r );
		return r * r * r;
	}
	public static void Main(){
		double vol = KubusVolume(2);
		Console.WriteLine("Het volume is {0}.", vol);
		vol = KubusVolume(6);
		Console.WriteLine("Het volume is {0}.", vol);
	}
}
```
https://dotnetfiddle.net/gBs2lL

- Oplossing oef 5.10


```C#
using System;

public class Program
{

private static double OppCirkel(double r) {
	double opp = r * r * Math.PI ;
	Console.WriteLine("Gegeven is straal {0}", r );
	return r * r * Math.PI;
}

public static void Main(){
	double opp = OppCirkel(2);
	Console.WriteLine("De opp is {0:0.00}.", opp);
	opp = OppCirkel(6);
	Console.WriteLine("De opp is {0:0.00}.", opp);
}
}
```
https://dotnetfiddle.net/kgCPlE

-Oplossing oef 6.7

```C#
public partial class MainWindow : Window
{
private Random ageGuesser = new Random();
private int tries = 0;

public MainWindow()
{
    InitializeComponent();

    label1.Content = Convert.ToString(ageGuesser.Next(5, 110));

}

private void button_Click(object sender, RoutedEventArgs e)
{
    tries = tries + 1;
    MessageBox.Show("Number of tries was " + tries);
    tries = 0;
    label1.Content = Convert.ToString(ageGuesser.Next(5, 110));
}

private void button1_Click(object sender, RoutedEventArgs e)
{
    label1.Content = Convert.ToString(ageGuesser.Next(5, 110));
    tries = tries + 1;
}
}
}
```

- Oplossing oef 6.8

```C#
public partial class MainWindow : Window
{
    private Random randomNumber = new Random();
    private double x, y, size;
    private SolidColorBrush brush;
    private DispatcherTimer timer = new DispatcherTimer();

public MainWindow()
{
    InitializeComponent();
    gapLabel.Content = Convert.ToString(gapSlider.Value);
    brush = new SolidColorBrush(Colors.Black);
    timer.Interval = TimeSpan.FromSeconds(gapSlider.Value);
    timer.Tick += timer_Tick;
}

private void Start_Click(object sender, RoutedEventArgs e)
{
    timer.Start();
}

private void Stop_Click(object sender, RoutedEventArgs e)
{
    timer.Stop();
}

private void gapSlider_ValueChanged_1(object sender, RoutedPropertyChangedEventArgs<double> e)
{

    int timeGap = Convert.ToInt32(gapSlider.Value);
    gapLabel.Content = Convert.ToString(timeGap);

}

private void Clear_Click(object sender, RoutedEventArgs e)
{
    paperCanvas.Children.Clear();
}

private void timer_Tick(object sender, EventArgs e)
{
    x = randomNumber.Next(0, Convert.ToInt32(paperCanvas.Width));
    y = randomNumber.Next(0, Convert.ToInt32(paperCanvas.Height));
    size = randomNumber.Next(15);

    Ellipse ellipse = new Ellipse();
    ellipse.Width = size;
    ellipse.Height = size;
    ellipse.Stroke = new SolidColorBrush(Colors.White);
    ellipse.Fill = brush;
    ellipse.Margin = new Thickness(x, y, 0, 0);
    paperCanvas.Children.Add(ellipse);

    // set new timer interval
    timer.Stop();
    int ms = randomNumber.Next(1, Convert.ToInt32(gapSlider.Value));
    timer.Interval = TimeSpan.FromMilliseconds(ms);
    timer.Start();
}
```

###Projectjes
- Refactoring van een CookcieClicker van MichielVE

```C#
public partial class MainWindow : Window
{
long aantKliks = 0;

public MainWindow()
{
    InitializeComponent();
}

private void Coockie_MouseEnter(object sender, MouseEventArgs e)
{
    Coockie.Fill = new SolidColorBrush(Colors.SaddleBrown);
    Coockie.StrokeThickness = 4;
    Coockie.Stroke = new SolidColorBrush(Colors.Black);
}

private void Coockie_MouseLeave(object sender, MouseEventArgs e)
{
    Coockie.Fill = new SolidColorBrush(Colors.Gray);
    Coockie.StrokeThickness = 2;
    Coockie.Stroke = new SolidColorBrush(Colors.Black);
}

private void Coockie_MouseLeftButtonDown(object sender, MouseButtonEventArgs e)
{
    if (aantKliks < 100)
    {
	aantKliks++;
	teller.Text = String.Format("{0}", aantKliks);
    }
    else 
    { 
	    aantKliks = aantKliks + 50;
	    teller.Text = String.Format("{0}", aantKliks);
    }
```

###Extra oefeningen

- Hoger/lager spelletje
```C#
public static void Main(string[] args)
{
	Console.Clear();
	Random rndGen = new Random();
	int g = rndGen.Next(0, 100);
	int gok = 100;
	int aantBeurten = 0;


	while (gok != g)
	{
	Console.WriteLine("Raad het getal:");
	string input = Console.ReadLine();
	if (gok == g)
	{
	    break;
	    Console.WriteLine("Doei");
	}
	gok = Convert.ToInt32(input);

	if (gok < g)
	{
	    Console.WriteLine("Hoger");

	    aantBeurten++;
	}
	else if (gok == g)
	{   
	    Console.WriteLine("Goedzo");
	    Console.WriteLine("Je deed er {0} beurten over.", aantBeurten);
	}
	else
	{
	    Console.WriteLine("Lager");

	    aantBeurten++;
	}
}
```
