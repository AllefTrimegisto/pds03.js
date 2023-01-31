# pds03.js
Aplique o padrão de projeto decorator para criar um sanduíche de frango assado com pepperoni e queijo mussarela ralado. O projeto deve seguir os seguintes critérios:
- deve imprimir no console: Sanduíche de Carne, Bacon, QueijoMussarelaRalado custa $7,49.
- o sanduíche de frango assado custa $4,50.
- o ingrediente adicional pepperoni custa $0,99.
- o ingrediente adicional queijo mussarela ralado custa $2,00
- crie as classes necessárias: FrangoAssado, Pepperoni e QueijoMussarelaRala

class Sanduiche {
    protected double preco;
    protected String ingredientes;
    
    public Sanduiche() {
        preco = 4.50;
        ingredientes = "Sanduíche de frango assado";
    }
    
    public double getPreco() {
        return preco;
    }
    
    public String getIngredientes() {
        return ingredientes;
    }
}

class Pepperoni extends Sanduiche {
    public Pepperoni(Sanduiche sanduiche) {
        preco = sanduiche.getPreco() + 0.99;
        ingredientes = sanduiche.getIngredientes() + ", Pepperoni";
    }
}

class QueijoMussarelaRalado extends Sanduiche {
    public QueijoMussarelaRalado(Sanduiche sanduiche) {
        preco = sanduiche.getPreco() + 2.00;
        ingredientes = sanduiche.getIngredientes() + ", Queijo Mussarela Ralado";
    }
}

public class Decorator {
    public static void main(String[] args) {
        Sanduiche sanduiche = new Sanduiche();
        sanduiche = new Pepperoni(sanduiche);
        sanduiche = new QueijoMussarelaRalado(sanduiche);
        
        System.out.println(sanduiche.getIngredientes() + " custa $" + sanduiche.getPreco());
    }
}
Sanduíche de frango assado, Pepperoni, Queijo Mussarela Ralado custa $7.49

