# pbo-module-task
TUGAS PBO PRAKTIKUM
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Tugas_Pratikum
{
    // Processor
    public class Processor
    {
        public string merk, tipe;
    }
    public class Intel : Processor
    {
        public Intel()
        {
            base.merk = "Intel";
        }
    }
    public class Amd : Processor
    {
        public Amd()
        {
            base.merk = "AMD";
        }
    }
    public class CoreI3 : Intel
    {
        public CoreI3()
        {
            base.tipe = "Core I3";
        }
    }
    public class CoreI5 : Intel
    {
        public CoreI5()
        {
            base.tipe = "Core I5";
        }
    }
    public class CoreI7 : Intel
    {
        public CoreI7()
        {
            base.tipe = "Core I7";
        }
    }
    public class Ryazen : Amd
    {
        public Ryazen()
        {
            base.tipe = "RAYZEN";
        }
    }
    public class Athlon : Amd
    {
        public Athlon()
        {
            base.tipe = "ATHLON";
        }
    }

    // Vga
    public class Vga
    {
        public string merk;
    }
    public class Nvidia : Vga
    {
        public Nvidia()
        {
            base.merk = "Nvidia";
        }
    }
    public class AMD : Vga
    {
        public AMD()
        {
            base.merk = "AMD";
        }
    }

    // Laptop
    public class Laptop
    {
        public string merk, tipe;
        public Vga vga; 
        public Processor processor;

        public void LaptopDinyalakan()
        {
            Console.WriteLine($"Laptop {merk} {tipe} meneyala");
        }
        public void LaptopDimatikan()
        {
            Console.WriteLine($"Laptop {merk} {tipe} mati");
        }
    }
    public class Asus : Laptop
    {
        public Asus()
        {
            base.merk = "ASUS";
        }
    }
    public class Acer : Laptop
    {
        public Acer()
        {
            base.merk = "ACER";
        }
    }
    public class Lenovo : Laptop
    {
        public Lenovo()
        {
            base.merk = "Lenovo";
        }
    }
    public class Rog : Asus
    {
        public Rog()
        {
            base.tipe = "ROG";
        }
    }
    public class Vivobook : Asus
    {
        public Vivobook()
        {
            base.tipe = "Vivobook";
        }
        public void Ngoding()
        {
            Console.WriteLine("Ctak Ctak Ctak, error lagi!!");
        }
    }
    public class Swift : Acer
    {
        public Swift()
        {
            base.tipe = "Swift";
        }
    }
    public class Predator : Acer
    {
        public Predator()
        {
            base.tipe = "Predator";
        }
        public void BermainGame()
        {
            Console.WriteLine($"Laptop {merk} {tipe} sedang bermain game");
        }
    }
    public class Ideapad : Lenovo
    {
        public Ideapad()
        {
            base.tipe = "Ideapad";
        }
    }
    public class Legion : Lenovo
    {
        public Legion()
        {
            base.tipe = "Legion";
        }
    }
    internal class program
    {
        private static Laptop laptop1;
        private static Laptop laptop2;
        private static Predator predator;
        private static Acer acer;

        static void Main(string[] args)
        {
            laptop1 = new Vivobook();
            laptop1.vga = new Nvidia();
            laptop1.processor = new CoreI5();

            laptop2 = new Ideapad();
            laptop2.vga = new AMD();
            laptop2.processor = new Ryazen();

            predator = new Predator();
            predator.vga = new AMD();
            predator.processor = new CoreI7();

            // soal 1 laptop 2
            Console.WriteLine("soal 1");
            laptop2.LaptopDinyalakan();
            laptop2.LaptopDimatikan();

            // soal 2 laptop 1
            Console.WriteLine("soal 2");
            //laptop1.Ngoding(); // iki error soale kayae dia berusaha akses class anaknya sedangkan dia udah di dibuat dengan tipe laptop

            // soal 3
            Console.WriteLine("soal 3");
            Console.WriteLine(laptop1.vga.merk);
            Console.WriteLine(laptop1.processor.merk);
            Console.WriteLine(laptop1.processor.tipe);

            // soal 4
            Console.WriteLine("soal 4");
            predator.BermainGame();

            // soal 5
            acer = new Predator();
            //acer.BermainGame(); // iki error soale kayae dia berusaha akses class anaknya sedangkan dia udah di dibuat dengan tipe laptop

            // soal 6
            // kesimpulan semangat
            // sama ini kayae kalau variable yang udah dibuat sama tipe yang diatas dari anak2nya itu ngga bisa akses method anaknya
            // tapi kalau variable dibuat sama tipe data yang anak kaya predator itu dapat manggil method yang dimiliki emaknya
            // tp kamu cari tahu lagi aku takut salah kalo salah maap heheh aku juga belajar
        }
    }
}
