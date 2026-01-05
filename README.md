// यूज़र क्लास
public class User {
    private String username;
    private String password;

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    // यूज़र ऑथेंटिकेशन मेथड
    public boolean authenticate(String inputUsername, String inputPassword) {
        return this.username.equals(inputUsername) && this.password.equals(inputPassword);
    }
}

// प्रोडक्ट क्लास
public class Product {
    private String productId;
    private String name;
    private double price;

    public Product(String productId, String name, double price) {
        this.productId = productId;
        this.name = name;
        this.price = price;
    }

    // प्रोडक्ट डिटेल्स मेथड
    public void displayProduct() {
        System.out.println("Product ID: " + productId + ", Name: " + name + ", Price: " + price);
    }
}

// ऑर्डर क्लास
public class Order {
    private Product product;
    private int quantity;
    private boolean isCOD;

    public Order(Product product, int quantity, boolean isCOD) {
        this.product = product;
        this.quantity = quantity;
        this.isCOD = isCOD;
    }

    // ऑर्डर प्रोसेसिंग मेथड
    public void processOrder() {
        System.out.println("Processing order for product: " + product.productId);
        System.out.println("Quantity: " + quantity);
        if (isCOD) {
            System.out.println("Payment method: Cash on Delivery");
        } else {
            System.out.println("Payment method: Prepaid");
        }
        // ऑर्डर प्रोसेसिंग की अन्य लॉजिक यहाँ जोड़ी जा सकती है
    }
}

// मेन क्लास
public class DropShippingPlatform {
    public static void main(String[] args) {
        // यूज़र उदाहरण
        User user = new User("john_doe", "password123");
        boolean isAuthenticated = user.authenticate("john_doe", "password123");
        if (isAuthenticated) {
            System.out.println("User authenticated successfully.");
        } else {
            System.out.println("Authentication failed.");
        }

        // प्रोडक्ट उदाहरण
        Product product = new Product("P123", "Smartphone", 299.99);
        product.displayProduct();

        // ऑर्डर उदाहरण
        Order order = new Order(product, 2, true);
        order.processOrder();
    }
}
