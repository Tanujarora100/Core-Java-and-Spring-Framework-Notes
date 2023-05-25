```java
   public static void main(String[] args) {
        // Create an instance of ModelMapper
        ModelMapper modelMapper = new ModelMapper();

        // Create an Order entity object
        Order order = new Order();
        order.setCustomerNumber(123);
        order.setShippingAddress("123 Shipping Street");
        order.setBillingAddress("456 Billing Street");

        Order order2= new Order();
        order2.setCustomerNumber(488);
        order2.setShippingAddress("789 Shipping Street");
        order2.setBillingAddress("B138 Billing ");


        PropertyMap<Order, orderDTO> propertyMap = new PropertyMap<Order, orderDTO>() {
            @Override
            protected void configure() {
                map().setCustomerName(String.valueOf(source.getCustomerNumber()));
                map().setShippingStreetAddress(source.getShippingAddress());
                map().setBillingStreetAddress(source.getBillingAddress());
            }
        };
        modelMapper.addMappings(propertyMap);

        orderDTO dto = modelMapper.map(order,orderDTO.class);
        orderDTO dto2= modelMapper.map(order2,orderDTO.class);

        // Print the mapped OrderDTO object
        System.out.println("Customer Name: " + dto.getCustomerName());
        System.out.println("Shipping Street Address: " + dto.getShippingStreetAddress());
        System.out.println("Billing Street Address: " + dto.getBillingStreetAddress());

        System.out.println("Customer Name: " + dto2.getCustomerName());
        System.out.println("Shipping Street Address: " + dto2.getShippingStreetAddress());
        System.out.println("Billing Street Address: " + dto2.getBillingStreetAddress());
    }
    ```