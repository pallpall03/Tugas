package Java;
// Kelas Induk
abstract class BangunDatar {
    abstract double luas();
    abstract double keliling();
}

// Kelas Turunan: Persegi
class Persegi extends BangunDatar {
    private double sisi;

    public Persegi(double sisi) {
        this.sisi = sisi;
    }

    @Override
    public double luas() {
        return sisi * sisi;
    }

    @Override
    public double keliling() {
        return 4 * sisi;
    }
}

// Kelas Turunan: Lingkaran
class Lingkaran extends BangunDatar {
    private double r;

    public Lingkaran(double r) {
        this.r = r;
    }

    @Override
    public double luas() {
        return Math.PI * r * r;
    }

    @Override
    public double keliling() {
        return 2 * Math.PI * r;
    }
}

// Kelas Turunan: Segitiga
class Segitiga extends BangunDatar {
    private double alas, tinggi;

    public Segitiga(double alas, double tinggi) {
        this.alas = alas;
        this.tinggi = tinggi;
    }

    @Override
    public double luas() {
        return 0.5 * alas * tinggi;
    }

    @Override
    public double keliling() {
        // Asumsi segitiga sama kaki
        double sisiMiring = Math.sqrt((alas / 2) * (alas / 2) + tinggi * tinggi);
        return alas + (2 * sisiMiring);
    }
}

// Kelas Main untuk menjalankan program
public class Pholimorpysm {
    public static void main(String[] args) {
        // Objek Persegi
        Persegi persegi = new Persegi(4);
        System.out.println("Luas Persegi: " + persegi.luas());
        System.out.println("Keliling Persegi: " + persegi.keliling());

        // Objek Lingkaran
        Lingkaran lingkaran = new Lingkaran(7);
        System.out.println("Luas Lingkaran: " + lingkaran.luas());
        System.out.println("Keliling Lingkaran: " + lingkaran.keliling());

        // Objek Segitiga
        Segitiga segitiga = new Segitiga(6, 8);
        System.out.println("Luas Segitiga: " + segitiga.luas());
        System.out.println("Keliling Segitiga: " + segitiga.keliling());
    }
}

