Practica principio SOLID

class Order
  def initialize(items)
    @items = items
  end

  def calculate_total
    total = 0
    @items.each do |item|
      total += item.price
    end
    total
  end

  def send_confirmation_email
    # Lógica para enviar un correo electrónico de confirmación
    puts "Email enviado a customer@example.com"
  end

  def print_order
    @items.each do |item|
      puts "Item: #{item.name} - Price: #{item.price}"
    end
  end
end

class Item
  attr_accessor :name, :price

  def initialize(name, price)
    @name = name
    @price = price
  end
end

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

++Refactoring++

class Order
  attr_reader :items
  
  def initialize(items)
	@items = items
  end
end
	

class Price
  def self.calculate(order)
    order.items.sum(&:price)
    end
  end

class OrderEmail
  def self.send_confirmation(order,email)
    total = Price.calculate(order)
    puts "Email enviado a #{email} con total #{total}"
  end
end

class OrderPrinter
  def self.print(order)
    order.items.each do |item|
      puts "Item: #{item.name} - Price: #{item.price}"
    end
  end
end

class Item
  attr_reader :name, :price

  def initialize(name, price)
    @name = name
    @price = price
  end
end

items = Item.new("Libro", 10)
item2 = Item.new("Lapiz", 5)

order = Order.new([item1, item2])

OrderPrinter.print(order)
OrderEmail.send_confirmation(order, "cliente@email.com")