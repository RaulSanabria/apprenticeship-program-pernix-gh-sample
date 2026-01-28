public class User {
    private String name;
    private String address;
    private String phone;
    private String email;
    private int loyaltyPoints;
    private double accountBalance;
    private List<String> orders;
    private List<String> coupons;

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Aca el code smell es el "clase grande" tiene demasiadas funcionalidades diferentes
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

    // Method to update user information

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Aca el code smell es el "Lista larga de parametros" aca hay demasiados parametros
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    public void updateInfo(String name, String address, String phone, String email) {
        this.name = name;
        this.address = address;
        this.phone = phone;
        this.email = email;
    }

    // Method to calculate discount based on loyalty points
    public double calculateDiscount(int loyaltyPoints, double accountBalance) {
        double discount = 0.0;
        if (loyaltyPoints > 100) {
            discount = accountBalance * 0.1;
        } else if (loyaltyPoints > 200) {
            discount = accountBalance * 0.2;
        } else {
            discount = accountBalance * 0.05;
        }
        return discount;
    }


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Aca el code smell es el "Codigo duplicado" debido a que ambas funciones imprimen de misma manera.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

    // Method to print all orders
    public void printOrders() {
        for (String order : orders) {
            System.out.println("Order: " + order);
        }
    }

    // Method to apply coupons
    public void applyCoupons(List<String> coupons) {
        for (String coupon : coupons) {
            System.out.println("Applying coupon: " + coupon);
        }
    }

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Aca el code smell es el "Codigo muerto" esto ya no hace nada esta deprecated
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

    // Deprecated method
    public void deprecatedMethod() {
        // This method is no longer used
    }
}

