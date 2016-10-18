# Portfolio

`#CSharp`
  
- Oplossing oef 5.9


	```
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


	```
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

