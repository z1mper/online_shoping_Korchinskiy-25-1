
abstract class CatalogItem {
    public String title;
    public double price;

    public CatalogItem(String title, double price) {
        this.title = title;
        this.price = price;
    }


    public abstract double calculatePrice(int quantity);
}


abstract class CatalogItemWithMap extends CatalogItem {
    public HashMap<String, Object> additionalData;

    public CatalogItemWithMap(String title, double price) {
        super(title, price);
        additionalData = new HashMap<>();
    }

    public void addData(String key, Object value) {
        additionalData.put(key, value);
    }

    public Object getData(String key) {
        return additionalData.get(key);
    }
}

    @Override
    public double calculatePrice(int quantity) {
        return price * quantity; // Простая реализация
    }

    public String getModel() {
        return model;
    }

    public String getBrand() {
        return brand;
    }
}


class GardenItem extends CatalogItemWithMap {
    private String plantType;
    private int quantityInPackage;

    public GardenItem(String title, double price, String plantType, int quantityInPackage) {
        super(title, price);
        this.plantType = plantType;
        this.quantityInPackage = quantityInPackage;
    }
