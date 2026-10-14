// =====================================================================
// PRÁCTICA 6: HERENCIA Y RELACIONES ANIDADAS
// "SISTEMA DE GESTIÓN DE VEHÍCULOS PARA UNA EMPRESA DE SERVICIOS TÉCNICOS"
// =====================================================================

// ---------------------------------------------------------------------
// CLASE MOTOR
// No hereda de nadie y no depende de ninguna otra clase.
// Es la clase que será "contenida" dentro de Vehiculo (relación anidada).
// ---------------------------------------------------------------------

class Motor {
    private String tipoCombustible;
    private int cilindros;
    private int potencia; // en HP

    public Motor(String tipoCombustible, int cilindros, int potencia) {
        this.tipoCombustible = tipoCombustible;
        this.cilindros = cilindros;
        this.potencia = potencia;
    }

    public void mostrarMotor() {
        System.out.println("Tipo de combustible: " + tipoCombustible);
        System.out.println("Cilindros: " + cilindros);
        System.out.println("Potencia: " + potencia + " HP");
    }
}

// ---------------------------------------------------------------------
// CLASE VEHICULO (clase padre / superclase)
// ---------------------------------------------------------------------
class Vehiculo {
    protected String marca;
    protected String modelo;
    protected int anio;

    // RELACIÓN ANIDADA: Vehículo contiene un objeto Motor
    // (Vehiculo "TIENE UN" Motor -> composición/agregación, NO herencia)
    protected Motor motor;

    public Vehiculo(String marca, String modelo, int anio, Motor motor) {
        this.marca = marca;
        this.modelo = modelo;
        this.anio = anio;
        this.motor = motor; // aquí se "ensambla" el objeto Motor dentro de Vehiculo
    }

    public void mostrarInformacion() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + anio);
        // Vehiculo usa (delega en) el método de su objeto Motor
        motor.mostrarMotor();
    }
}

// ---------------------------------------------------------------------
// CLASE AUTOMOVIL
// HERENCIA: Automóvil hereda de Vehículo (Automóvil "ES UN" Vehículo)
// ---------------------------------------------------------------------
class Automovil extends Vehiculo { // <-- HERENCIA aquí (extends)
    private int numeroPuertas;

    public Automovil(String marca, String modelo, int anio, Motor motor, int numeroPuertas) {
        super(marca, modelo, anio, motor); // reutiliza el constructor de Vehiculo
        this.numeroPuertas = numeroPuertas;
    }

    @Override
    public void mostrarInformacion() {
        System.out.println("===== AUTOMÓVIL =====");
        super.mostrarInformacion(); // reutilización de código heredado de Vehiculo
        System.out.println("Número de puertas: " + numeroPuertas);
    }
}

// ---------------------------------------------------------------------
// CLASE CAMIONETA
// HERENCIA: Camioneta hereda de Vehículo
// ---------------------------------------------------------------------
class Camioneta extends Vehiculo { // <-- HERENCIA aquí (extends)
    private double capacidadCarga; // en kg

    public Camioneta(String marca, String modelo, int anio, Motor motor, double capacidadCarga) {
        super(marca, modelo, anio, motor);
        this.capacidadCarga = capacidadCarga;
    }

    @Override
    public void mostrarInformacion() {
        System.out.println("===== CAMIONETA =====");
        super.mostrarInformacion();
        System.out.println("Capacidad de carga: " + capacidadCarga + " kg");
    }
}

// ---------------------------------------------------------------------
// CLASE MOTOCICLETA
// HERENCIA: Motocicleta hereda de Vehículo
// ---------------------------------------------------------------------
class Motocicleta extends Vehiculo { // <-- HERENCIA aquí (extends)
    private int cilindrada; // en cc

    public Motocicleta(String marca, String modelo, int anio, Motor motor, int cilindrada) {
        super(marca, modelo, anio, motor);
        this.cilindrada = cilindrada;
    }

    @Override
    public void mostrarInformacion() {
        System.out.println("===== MOTOCICLETA =====");
        super.mostrarInformacion();
        System.out.println("Cilindrada: " + cilindrada + " cc");
    }
}

// ---------------------------------------------------------------------
// CLASE AUTOBUS (RETO PARA EL ESTUDIANTE - punto 12)
// HERENCIA: Autobús hereda de Vehículo
// RELACIÓN ANIDADA: hereda el atributo "motor" de Vehículo, que ya es
//                    un objeto de la clase Motor.
// ---------------------------------------------------------------------
class Autobus extends Vehiculo { // <-- HERENCIA aquí (extends)
    private int numeroPasajeros;

    public Autobus(String marca, String modelo, int anio, Motor motor, int numeroPasajeros) {
        super(marca, modelo, anio, motor); // RELACIÓN ANIDADA: se pasa el objeto Motor al padre
        this.numeroPasajeros = numeroPasajeros;
    }

    @Override
    public void mostrarInformacion() {
        System.out.println("===== AUTOBÚS =====");
        super.mostrarInformacion();
        System.out.println("Número de pasajeros: " + numeroPasajeros);
    }
}

// ---------------------------------------------------------------------
// CLASE PRINCIPAL (main)
// ---------------------------------------------------------------------
public class SistemaVehiculos {
    public static void main(String[] args) {

        // Creamos primero los objetos Motor (RELACIÓN ANIDADA en acción:
        // cada Vehiculo va a "tener" uno de estos objetos)
        Motor motorAuto = new Motor("Gasolina", 4, 150);
        Motor motorCamioneta = new Motor("Diesel", 6, 250);
        Motor motorMoto = new Motor("Gasolina", 2, 50);
        Motor motorBus = new Motor("Diesel", 6, 300);

        // Creamos los objetos de las clases hijas (HERENCIA en acción)
        Automovil auto = new Automovil("Toyota", "Corolla", 2024, motorAuto, 4);
        Camioneta camioneta = new Camioneta("Ford", "Ranger", 2023, motorCamioneta, 1000.0);
        Motocicleta moto = new Motocicleta("Honda", "CBR", 2024, motorMoto, 500);
        Autobus bus = new Autobus("Mercedes-Benz", "Citaro", 2022, motorBus, 40);

        // Mostramos la información de cada vehículo
        auto.mostrarInformacion();
        System.out.println();
        camioneta.mostrarInformacion();
        System.out.println();
        moto.mostrarInformacion();
        System.out.println();
        bus.mostrarInformacion();
    }
}