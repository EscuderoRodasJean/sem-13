# sem-13****

import javax.swing.DefaultComboBoxModel;
import javax.swing.DefaultListModel;
import javax.swing.JOptionPane;



public class Ventana1 extends javax.swing.JFrame {

    DefaultListModel<String>modeloLista;
    DefaultComboBoxModel<String>modeloCombo;

    public Ventana1() {
        
        initComponents();
        
        modeloLista=new DefaultListModel();
        lstPrincipal.setModel(modeloLista);
        
        modeloCombo=new DefaultComboBoxModel();
        cboPrincipal.setModel(modeloCombo);
        
        // modeloCombo=modeloLista;
    }
    
    private void actualizarListaCombo(){
        //limpiarElementos
        modeloCombo.removeAllElements();
        
        //agregar todos los elementos del modeloLista al modeloCombo
        for (int i = 0; i <modeloLista.getSize(); i++) {
            modeloCombo.addElement(modeloLista.getElementAt(i));
        }
    
    }

    
    
    
    
    
    
    
    
    
    
    
    
    
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        jScrollPane1 = new javax.swing.JScrollPane();
        lstPrincipal = new javax.swing.JList<>();
        btnListaAgregar = new javax.swing.JButton();
        btnListaModificar = new javax.swing.JButton();
        btnPropiedades = new javax.swing.JButton();
        btnListaEliminar = new javax.swing.JButton();
        textBuscar = new javax.swing.JTextField();
        jLabel1 = new javax.swing.JLabel();
        btnListaBuscar = new javax.swing.JButton();
        cboPrincipal = new javax.swing.JComboBox<>();
        btnListaMostrar = new javax.swing.JButton();
        rbVerListaCasilla = new javax.swing.JRadioButton();
        rbVerListaDialogo = new javax.swing.JRadioButton();
        jScrollPane2 = new javax.swing.JScrollPane();
        txtVerLista = new javax.swing.JTextArea();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        lstPrincipal.setBackground(new java.awt.Color(204, 255, 204));
        lstPrincipal.setModel(new javax.swing.AbstractListModel<String>() {
            String[] strings = { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" };
            public int getSize() { return strings.length; }
            public String getElementAt(int i) { return strings[i]; }
        });
        jScrollPane1.setViewportView(lstPrincipal);

        btnListaAgregar.setText("Agregar");
        btnListaAgregar.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnListaAgregarActionPerformed(evt);
            }
        });

        btnListaModificar.setText("Modificar");
        btnListaModificar.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnListaModificarActionPerformed(evt);
            }
        });

        btnPropiedades.setText("Propiedades");
        btnPropiedades.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnPropiedadesActionPerformed(evt);
            }
        });

        btnListaEliminar.setText("Eliminar");
        btnListaEliminar.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnListaEliminarActionPerformed(evt);
            }
        });

        textBuscar.setText("jTextField1");

        jLabel1.setText("Elemento");

        btnListaBuscar.setBackground(new java.awt.Color(204, 204, 204));
        btnListaBuscar.setFont(new java.awt.Font("Showcard Gothic", 0, 12)); // NOI18N
        btnListaBuscar.setForeground(new java.awt.Color(0, 0, 0));
        btnListaBuscar.setText("Buscar");
        btnListaBuscar.setAlignmentY(0.0F);
        btnListaBuscar.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnListaBuscarActionPerformed(evt);
            }
        });

        cboPrincipal.setBackground(new java.awt.Color(255, 51, 51));
        cboPrincipal.setModel(new javax.swing.DefaultComboBoxModel<>(new String[] { "Item 1", "Item 2", "Item 3", "Item 4" }));
        cboPrincipal.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                cboPrincipalActionPerformed(evt);
            }
        });

        btnListaMostrar.setText("Mostrar lista");
        btnListaMostrar.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnListaMostrarActionPerformed(evt);
            }
        });

        rbVerListaCasilla.setText("Ver lista en casilla interior");

        rbVerListaDialogo.setText("Ver lista en cuadro de dialogo");

        txtVerLista.setColumns(20);
        txtVerLista.setRows(5);
        jScrollPane2.setViewportView(txtVerLista);

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(27, 27, 27)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(layout.createSequentialGroup()
                                .addComponent(btnListaMostrar)
                                .addGap(54, 54, 54)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(rbVerListaDialogo)
                                    .addComponent(rbVerListaCasilla)))
                            .addGroup(layout.createSequentialGroup()
                                .addComponent(jLabel1)
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addComponent(btnListaBuscar))
                            .addGroup(layout.createSequentialGroup()
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING, false)
                                    .addComponent(cboPrincipal, javax.swing.GroupLayout.Alignment.LEADING, 0, 117, Short.MAX_VALUE)
                                    .addComponent(jScrollPane1, javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(textBuscar, javax.swing.GroupLayout.Alignment.LEADING))
                                .addGap(85, 85, 85)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(btnListaAgregar, javax.swing.GroupLayout.PREFERRED_SIZE, 95, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(btnListaEliminar, javax.swing.GroupLayout.PREFERRED_SIZE, 95, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addGap(30, 30, 30)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(btnPropiedades, javax.swing.GroupLayout.PREFERRED_SIZE, 95, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(btnListaModificar, javax.swing.GroupLayout.PREFERRED_SIZE, 95, javax.swing.GroupLayout.PREFERRED_SIZE)))))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(35, 35, 35)
                        .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addContainerGap(205, Short.MAX_VALUE))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(42, 42, 42)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                            .addComponent(btnListaAgregar, javax.swing.GroupLayout.PREFERRED_SIZE, 40, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(btnListaModificar, javax.swing.GroupLayout.PREFERRED_SIZE, 40, javax.swing.GroupLayout.PREFERRED_SIZE))
                        .addGap(28, 28, 28)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                            .addComponent(btnListaEliminar, javax.swing.GroupLayout.PREFERRED_SIZE, 40, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(btnPropiedades, javax.swing.GroupLayout.PREFERRED_SIZE, 40, javax.swing.GroupLayout.PREFERRED_SIZE))
                        .addGap(170, 170, 170))
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                        .addGap(18, 18, 18)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                            .addComponent(jLabel1)
                            .addComponent(btnListaBuscar, javax.swing.GroupLayout.PREFERRED_SIZE, 31, javax.swing.GroupLayout.PREFERRED_SIZE))
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(textBuscar, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                        .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 203, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(18, 18, 18)
                        .addComponent(cboPrincipal, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(rbVerListaCasilla)
                        .addGap(9, 9, 9)
                        .addComponent(rbVerListaDialogo))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(16, 16, 16)
                        .addComponent(btnListaMostrar)))
                .addGap(18, 18, 18)
                .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(17, Short.MAX_VALUE))
        );

        pack();
    }// </editor-fold>                        

    private void btnListaAgregarActionPerformed(java.awt.event.ActionEvent evt) {                                                
        //Agregar un nuevo elemento al control lista
        String nuevoElemento=JOptionPane.showInputDialog("Ingrese nuevo Elemento");
        
        //Agregar elemnto a modelo Lista
        modeloLista.addElement(nuevoElemento);
        
        //Seleccionamos en el control lista el nuevo elemto a agregar
        lstPrincipal.setSelectedIndex(modeloLista.getSize()-1);
        
        actualizarListaCombo();
    }                                               

    private void btnListaModificarActionPerformed(java.awt.event.ActionEvent evt) {                                                  
        //modificar el valor del item seleccionado del control lista
        String seleccionado, modificado;
        int indiceSeleccionado;
        
        //capturar el inidice del elemnto seleccionado
        indiceSeleccionado= lstPrincipal.getSelectedIndex();
        
        //capturar el valor del elemnto seleccionado
        seleccionado = lstPrincipal.getSelectedValue();
        
        //mostrar el cuador de diaologo para el ingreso del nuevo valor
        modificado=JOptionPane.showInputDialog("Modificar "+seleccionado+" por: ");
        

                modeloLista.setElementAt(modificado,indiceSeleccionado);
                
                actualizarListaCombo();
    }                                                 

    private void btnListaEliminarActionPerformed(java.awt.event.ActionEvent evt) {                                                 
        modeloLista.removeElementAt(lstPrincipal.getSelectedIndex());
        
        actualizarListaCombo();
    }                                                

    private void cboPrincipalActionPerformed(java.awt.event.ActionEvent evt) {                                             
        // TODO add your handling code here:
    }                                            

    private void btnPropiedadesActionPerformed(java.awt.event.ActionEvent evt) {                                               
        String primerElemento, ultimoElemento, elementoSeleccionado;
        int cantElementos;
        
        primerElemento = modeloLista.getElementAt(0);
        ultimoElemento = modeloLista.getElementAt(modeloLista.getSize()-1);
        elementoSeleccionado = lstPrincipal.getSelectedValue();
        cantElementos= modeloLista.getSize();
                
                String salida = String.format("""
                                              >>Propiedades de lista:
                                              Primer elemento: %s
                                              Ultimo elemento: %s
                                              Elemento seleccionado: %s
                                              Cantidad de elemento: %s
                                              """);
                
                JOptionPane.showMessageDialog(rootPane, salida);
                
                actualizarListaCombo();
    }                                              

    private void btnListaMostrarActionPerformed(java.awt.event.ActionEvent evt) {                                                
 
        
        if( rbVerListaCasilla.isSelected()==true){
                txtVerLista.setText(modeloLista.toString());
                }
        if( rbVerListaDialogo.isSelected()==true){
            txtVerLista.setText("");
                JOptionPane.showMessageDialog(rootPane, modeloLista.toString());
                }
    }                                               

    private void btnListaBuscarActionPerformed(java.awt.event.ActionEvent evt) {                                               
        String buscado = txtBuscar.getText();
        
        boolean existe = modeloLista.contains(buscado);
        
        int indiceEncontrado= modeloLista.indexOf(buscado);
        
        if (existe) {
            JOptionPane.showMessageDialog(rootPane, "El elemento "+buscado+ "SI EXISTE"+"en el indice: "+ indiceEncontrado);
            lstPrincipal.setSelectedIndex(indiceEncontrado);
        } 
            else{
            JOptionPane.showMessageDialog(rootPane, "El elemento "+buscado+ "NO EXISTE"+"en la lista, que pena =(: ");
        }
    }                                              

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(Ventana1.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(Ventana1.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(Ventana1.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(Ventana1.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new Ventana1().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton btnListaAgregar;
    private javax.swing.JButton btnListaBuscar;
    private javax.swing.JButton btnListaEliminar;
    private javax.swing.JButton btnListaModificar;
    private javax.swing.JButton btnListaMostrar;
    private javax.swing.JButton btnPropiedades;
    private javax.swing.JComboBox<String> cboPrincipal;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JScrollPane jScrollPane1;
    private javax.swing.JScrollPane jScrollPane2;
    private javax.swing.JList<String> lstPrincipal;
    private javax.swing.JRadioButton rbVerListaCasilla;
    private javax.swing.JRadioButton rbVerListaDialogo;
    private javax.swing.JTextField textBuscar;
    private javax.swing.JTextArea txtVerLista;
    // End of variables declaration                   
}

