PSEUDOCODE from a simple calculator program

1. Creat Abstract Class 
package operasibilangan;				->> creat in folder(package) of operasibilangan

class OperasiBilanganAbs {				->> access public, class abstract
    	a,b,c;
	set_A(a)					->> access protected, type double, method abstract
	set_B(b)					->> access protected, type double, method abstract
	set_C()						->> access protected, method abstract
	get_A()						->> access protected, method abstract double
	get_B()						->> access protected, method abstract double
	get_C()						->> access protected, method abstract double
	tampil()					->> access protedted, method abstract
}

2. Creat "Operasi Penjumlahan" Class 
class OperasiPenjumlahan extends OperasiBilanganAbs	->> inheritance from class abstract OperasiBilanganAbs
	a, b, c						->> access protected, type double
	set_A(a)					->> access protected, type double, method abstract
		this.a=a;
	set_B(b)					->> access protected, type double, method abstract
		this.b=b;
	set_C()						->> access protected, method abstract
		try { c=a+b; }
		catch(IOException) { print message }	->> to check when there is an error
	get_A()						->> access protected, method abstract double
		return a;
	get_B()						->> access protected, method abstract double
		return b;
	get_C()						->> access protected, method abstract double
		return c;
	tampil()					->> access protedted, method abstract
		print a+b = c

*Note . . . enter the code "try" to check when there is an error in each "set_C ()" in the class : (step 3-5)
3. "Operasi Pengurangan" Class 		->> try { c=a-b; }
					    catch(IOException) { print message }

4. "Operasi Perkalian" Class		->> try { c=a*b; }
					    catch(IOException) { print message }
		 			    catch(DivideByZeroException) { print message }

5. "Operasi Pembagian" Class		->> try { c=a/b; }
					    catch(IOException) { print message }
		 			    catch(DivideByZeroException) { print message }
 
---------------------------------------------------------------------------------------------------------------
6. Final Class OperasiBilanganAbsCetak 			 
package operasibilangan;				->> creat in folder(package) of operasibilangan

final class OperasiBilanganAbsCetak 			->> access public, class final
    cetaksemua (OperasiBilanganAbs OB) 			->> access private, type double, method
    OB.set_A(0);					->> call and set method "set_A" to interger 0 to get an error signal
    OB.set_B(2.5);					->> call and set method "set_B" to 2.5
    OB.set_C();						->> call method "set_C"
    OB.tampil();					->> call method "tampil()"

    main(String[] args) 				->> main method
        OperasiBilanganAbs jumlah = new OperasiPenjumlahan();	->> new instantiate variable namely "jumlah" from class OperasiPenjumlahan 
        cetaksemua(jumlah);					->> show variable and content
        OperasiBilanganAbs kurang = new OperasiPengurangan();	->> new instantiate variable namely "kurang" from class OperasiPengurangan 
        cetaksemua(kurang);					->> show variable and content
        OperasiBilanganAbs kali = new OperasiPerkalian();	->> new instantiate variable namely "kali" from class OperasiPerkalian 
        cetaksemua(kali);					->> show variable and content
        OperasiBilanganAbs bagi = new OperasiPembagian();	->> new instantiate variable namely "bagi" from class OperasiPembagian 
        cetaksemua(bagi);					->> show variable and content
    }
}
      
