import javax.swing.*;            // Für grafische Elemente wie JFrame, JButton etc.
import java.awt.*;               // Für Layout-Management
import java.awt.event.*;         // Für Ereignisbehandlung (Button-Klicks)

// Hauptklasse des Rechners – erbt von JFrame (Fenster)
public class RechnerGUI extends JFrame {
    private JTextField tf1 = new JTextField(10);
    private JTextField tf2 = new JTextField(10);
    private JLabel     tfErgebnis = new JLabel("0.00", SwingConstants.RIGHT);

    private JButton btnPlus  = new JButton("+");
    private JButton btnMinus = new JButton("–");
    private JButton btnMal   = new JButton("*");
    private JButton btnTeil  = new JButton("/");
    private JButton btnClear = new JButton("Clear");
    private JButton btnExit  = new JButton("Exit");


    // Konstruktor: hier wird das Fenster aufgebaut
    public RechnerGUI() {
        setTitle("Taschenrechner");           // Fenstertitel
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // Fenster schließen bei Klick auf X

        // 1) Oberer Bereich: Eingaben
        JPanel panelInput = new JPanel(new GridLayout(2, 2, 5, 5));
        panelInput.add(new JLabel("  Zahl 1:"));
        panelInput.add(tf1);
        panelInput.add(new JLabel("  Zahl 2:"));
        panelInput.add(tf2);

        btnPlus.setPreferredSize(new Dimension(120, 80));
        btnMinus.setPreferredSize(new Dimension(120, 80));
        btnMal.setPreferredSize(new Dimension(120, 80));
        btnTeil.setPreferredSize(new Dimension(120, 80));

        // 2) Mittlerer Bereich: Operatoren
        JPanel panelOps = new JPanel(new FlowLayout(FlowLayout.CENTER, 10, 10));
        panelOps.add(btnPlus);
        panelOps.add(btnMinus);
        panelOps.add(btnMal);
        panelOps.add(btnTeil);

        panelOps.setPreferredSize(new Dimension(220, 200));
        add(panelOps, BorderLayout.CENTER);

        // 3) Unterer Bereich: Ergebnis + Aktionen
        JPanel panelResult = new JPanel(new BorderLayout(5, 0));
        panelResult.add(new JLabel("  Ergebnis:"), BorderLayout.WEST);
        tfErgebnis.setPreferredSize(new Dimension(60, 25));
        tfErgebnis.setBorder(BorderFactory.createLineBorder(Color.GRAY));
        tfErgebnis.setOpaque(true);
        panelResult.add(tfErgebnis, BorderLayout.CENTER);

        JPanel panelActions = new JPanel(new GridLayout(1, 2, 5, 5));
        panelActions.add(btnClear);
        panelActions.add(btnExit);

        JPanel panelBottom = new JPanel(new BorderLayout(0, 5));
        panelBottom.add(panelResult, BorderLayout.NORTH);
        panelBottom.add(panelActions, BorderLayout.SOUTH);

        // Gesamtes Fenster: BorderLayout mit Abständen
        setLayout(new BorderLayout(10, 10));
        add(panelInput,  BorderLayout.NORTH);
        add(panelOps,    BorderLayout.CENTER);
        add(panelBottom, BorderLayout.SOUTH);

        // Pack & anzeigen
        pack();
        setMinimumSize(new Dimension(250, 350));
        setLocationRelativeTo(null);
        setVisible(true);

        // ActionListener für den Plus-Button
        btnPlus.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                double a, b, summe;
                try {
                    a = Double.parseDouble(tf1.getText());
                    b = Double.parseDouble(tf2.getText());
                } catch (NumberFormatException ex) {
                    JOptionPane.showMessageDialog(RechnerGUI.this, "Bitte Gültige Zahl eingeben!");
                    return;
                }
                summe = a + b;
                String ausgabe = String.format("%.2f", summe);
                tfErgebnis.setText(ausgabe);
            }
        });

        // ActionListener für den Minus-Button
        btnMinus.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                double a, b, summe;
                try {
                    a = Double.parseDouble(tf1.getText());
                    b = Double.parseDouble(tf2.getText());
                } catch (NumberFormatException ex) {
                    JOptionPane.showMessageDialog(RechnerGUI.this, "Bitte Gültige Zahl eingeben!");
                    return;
                }
                summe = a - b;
                String ausgabe = String.format("%.2f", summe);
                tfErgebnis.setText(ausgabe);
            }
        });


        //ActionListener für Mal Button
        btnMal.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                double a, b,  summe;
                try {
                    a = Double.parseDouble(tf1.getText());
                    b = Double.parseDouble(tf2.getText());
                } catch (NumberFormatException ex) {
                    JOptionPane.showMessageDialog(RechnerGUI.this, "Bitte Gültige Zahl eingeben!");
                    return;
                }
                summe = a * b;
                String ausgabe = String.format("%.2f", summe);
                tfErgebnis.setText(ausgabe);
            }
        });

        //ActionListener für Geteilt Button
        btnTeil.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                double a, b;
                try {
                    a = Double.parseDouble(tf1.getText());
                    b = Double.parseDouble(tf2.getText());
                } catch (NumberFormatException ex) {
                    JOptionPane.showMessageDialog(
                            RechnerGUI.this,
                            "Bitte gültige ganze Zahlen eingeben!"
                    );
                    return;
                }

                if (b == 0) {
                    JOptionPane.showMessageDialog(
                            RechnerGUI.this,
                            "Division durch 0 nicht erlaubt!",
                            "Fehler",
                            JOptionPane.ERROR_MESSAGE
                    );
                    return;
                }

                double summe = a / b;
                String ausgabe = String.format("%.2f", summe);
                tfErgebnis.setText(ausgabe);
            }
        });


        // ActionListener für Clear Button
        btnClear.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                tf1.setText("");
                tf2.setText("");
                tfErgebnis.setText("");
            }
        });

        //ActionListener für Beenden Button
        btnExit.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.exit(0);
            }
        });

    }

    // main-Methode: Einstiegspunkt des Programms
    public static void main(String[] args) {
        new RechnerGUI();  // Objekt erzeugen – GUI wird geöffnet
    }
}
