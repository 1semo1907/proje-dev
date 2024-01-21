import java.util.Scanner;

public class Proje2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Bir kelime girin: ");
        String kelime = scanner.nextLine();

        if (isPalindrome(kelime)) {
            System.out.println(kelime + " bir palindromdur.");
        } else {
            System.out.println(kelime + " bir palindrom değildir.");
        }

        scanner.close();
    }

    public static boolean isPalindrome(String kelime) {
        
        String tersKelime = "";
        for (int i = kelime.length() - 1; i >= 0; i--) {
            tersKelime += kelime.charAt(i);
        }

        
        return kelime.equalsIgnoreCase(tersKelime);
    }
}
//proje 2


public class Proje12 {
    public static void main(String[] args) {
        String kelime = "Program";
        int uzunluk = kelime.length();

        for (int i = 0; i < uzunluk; i++) {
            
            kelime = kelime.substring(1) + kelime.charAt(0);
            System.out.println(kelime);
        }
    }
}
//proje 12


public class Proje19 {
	for (int i = 0; i < 5; i++){
		for (int j = 0; j <=i; j++){
			system.out.prints(s:"*");
		}	
		System.out.println();
	}
	for (int i = 4; i >= 1; i--){
		for (int j= 1; j <= i; j++){
			System.out.print();
		}
	}

}
//Proje4


public class Proje19 {
    
    private static String isim;
    private static String renk;
    private static String sahiplik;

    
    private Pazaryeri() {}

    
    public static void setPazaryeri(String isim, String renk, String sahiplik) {
        Pazaryeri.isim = isim;
        Pazaryeri.renk = renk;
        Pazaryeri.sahiplik = sahiplik;
    }

    
    public static void setIsimRenk(String isim, String renk) {
        Pazaryeri.isim = isim;
        Pazaryeri.renk = renk;
    }

    
    public static String getIsim() {
        return isim;
    }

    
    public static String getRenk() {
        return renk;
    }

   
    public static String getSahiplik() {
        return sahiplik;
    }

    
    public static String PazaryeriTuru() {
        return "belirsiz";
    }
}
Proje19


import java.util.Scanner;

public class Proje9 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ondalık bir sayı girin: ");
        int ondalikSayi = scanner.nextInt();

        String binarySayi = decimalToBinary(ondalikSayi);

        System.out.println("Binary karşılığı: " + binarySayi);

        scanner.close();
    }

    public static String decimalToBinary(int ondalikSayi) {
        
        return Integer.toBinaryString(ondalikSayi);

    }
}
//Proje9


import java.util.Scanner;

public class Proje6 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int sayi;
        int enBuyuk = Integer.MIN_VALUE;
        int girilmeSirasi = 0;

        for (int i = 1; i <= 10; i++) {
            System.out.print(i + ". sayıyı girin: ");
            sayi = scanner.nextInt();

            if (sayi > enBuyuk) {
                enBuyuk = sayi;
                girilmeSirasi = i;
            }
        }

        System.out.println("En büyük sayı: " + enBuyuk);
        System.out.println("En büyük sayı " + girilmeSirasi + ". sırada girildi.");

        scanner.close();
    }
}
//Proje6


public class Proje18 {
    private int Atmno;

    public ATM(int Atmno) {
        this.Atmno = Atmno;
    }

    public void parayatir(double miktar) {
        System.out.println(miktar + " TL yatırıldı.");
    }

    public void paracek(double miktar) {
        System.out.println(miktar + " TL çekildi.");
    }

    public boolean kayitkontrol(int HesapNo, String sifre) {
        if (HesapNo == 1234 && sifre.equals("1234")) {
            System.out.println("Kayıt doğrulandı.");
            return true;
        } 
	else {
            System.out.println("Kayıt doğrulanamadı.");
            return false;
        }
    }

    public static void main(String[] args) {
        ATM atm = new ATM(1);

        atm.parayatir(1000);
        atm.paracek(500);

        atm.kayitkontrol(1234, "1234");
    }
}
//proje18


import java.util.Scanner;

public class Proje16 {
    public static void main(String[] args) {
        String metin = "Merhaba nasılsınız? Örnek bir metin.";

        Scanner scanner = new Scanner(System.in);
        System.out.print("Aramak istediğiniz karakteri girin: ");
        char aranankarakter = scanner.next().charAt(0);

        int karaktersayisi = sayac(metin, aranankarakter);

        System.out.println("Metin içinde '" + aranankarakter + "' karakteri " + karaktersayisi + " kez bulunmaktadır.");

        scanner.close();
    }

    public static int sayac(String metin, char karakter) {
        int sayac = 0;

        for (int i = 0; i < metin.length(); i++) {
            if (metin.charAt(i) == karakter) {
                sayac++;
            }
        }

        return sayac;
    }
}
//Proje16


import java.time.LocalDate;
import java.time.Period;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class Proje14 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("İlk tarihi (GG.AA.YYYY) formatında girin: ");
        String tarihstr1 = scanner.next();

        System.out.print("İkinci tarihi (GG.AA.YYYY) formatında girin: ");
        String tarihstr2 = scanner.next();

        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd.MM.yyyy");

        LocalDate tarih1 = LocalDate.parse(tarihstr1, formatter);
        LocalDate tarih2 = LocalDate.parse(tarihstr2, formatter);

        Period fark = Period.between(tarih1, tarih2);

        System.out.println("Gün farkı: " + fark.getDays() + " gün");
        System.out.println("Ay farkı: " + fark.getMonths() + " ay");
        System.out.println("Yıl farkı: " + fark.getYears() + " yıl");

        scanner.close();
    }
}
//Proje14


import java.util.Scanner;
import java.util.Random;

public class Proje1 {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    Random random = new Random();

    int rastsayi = random.nextInt(100) + 1;

    System.out.println("1 ile 100 arasında bir sayı belirlendi. Tahmininizi yapınız.");

    int tahminsayisi;
    int denemesayisi = 0;

    do {
      System.out.print("Tahmininiz: ");
      tahminsayisi = scanner.nextInt();
      denemesayisi++;

      if (tahminsayisi > rastsayi) {
        System.out.println("Daha küçük bir sayı girin.");
      } else if (tahminsayisi < rastsayi) {
        System.out.println("Daha büyük bir sayı girin.");
      } 
	else {
        if (denemesayisi == 1) {
          System.out.println("Tebrikler! İlk seferde sayıyı doğru tahmin ettiniz.");
        } 
	else {
          System.out.println("Tebrikler! Sayıyı " + denemeSayisi + " denemede buldunuz.");
        }
      }
    } while (tahmin != rastsayi);

    scanner.close();
  }
}
//Proje1
