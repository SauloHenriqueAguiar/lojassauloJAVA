# lojassauloJAVA

package com.mycompany.cliente;

public class ClienteVip extends cliente {
    
    private float creditoExtra;
    
    
    
    public ClienteVip(String nome, String email, float credito,float creditoExtra) {
        super(nome, email, credito);
        this.creditoExtra =  creditoExtra;
        
    }

    
    @Override
    public String toString() {
        return "ClienteVip:" + super.toString() +  "creditoExtra=" + creditoExtra + '}';
    }
    
    @Override
    public boolean fazerCompra(float valor){
       if (valor > creditoExtra+ super.getCredito()){
           return false;
       }else{
           super.setCredito(super.getCredito()-valor);
           return true;
       } 
    }
}

