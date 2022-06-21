
import javax.swing.JOptionPane;
import java.lang.NumberFormatException;

/**
 * @version May 30, 2013
 * @author Bujar Asllani
 */
public class Lottary6from36 {

    private Integer number, ranNumber, TOTAL_NUM = 6;
    private int[] userNumbers = new int[TOTAL_NUM];//Vargu ku ruhen numrat e dhene nga shfrytzuesi.
    private int[] lottoNumbers = new int[TOTAL_NUM];//Vargu ku ruhen numrat e gjeneruar nga kompjuteri.
    String label;

    public void inputData() {
        JOptionPane.showMessageDialog(null, "Miresevini ne lotarin 6 nga 36.\nMund te shtypni numra nga 1 deri ne 36.\nPer te ndaluar lojen shkruani 'exit'");
        System.out.println("Ju lutem shtypni 6(gjashte) numrat e fatit: ");
        int i = 0;
        int j = 0;
        String rez = "";
        while (i < TOTAL_NUM) {
            try {
                if ("".equals(rez)) {
                    label = JOptionPane.showInputDialog("Ju lutem shtypni numrin e [" + (i + 1) + "] :");
                    number = new Integer(label).intValue();
                    
                } else {     
                    label = JOptionPane.showInputDialog("Ju lutem shtypni numrin e [" + (i + 1) + "] : \nJu keni zgjedhur keta numra: \n" + rez);
                    number = new Integer(label).intValue();                    
                    
                }
                boolean checkRpt = checkRpt(userNumbers, number);
                if (number < 1 || number > 36) {
                    JOptionPane.showMessageDialog(null, "Numri " + number + " nuk eshte i pranueshem. \nJu lutem jepni nje numer nga 1 deri ne 36");
                } else if (checkRpt == false) {
                    JOptionPane.showMessageDialog(null, "Numrin [" + number + "] e keni zgjedhur nje here. \nJu lutem zgjedhni nje numer tjeter.");
                } else {
                    userNumbers[i] = number;
                    rez = rez + " [" + number + "]";
                    i++;
                }
            } catch (NumberFormatException s) {
                if("exit".equals(label))
                    System.exit(0);
                else
                JOptionPane.showMessageDialog(null, "!!! Keni shtypur nje karakter te gabuar ose keni lene zbrazet!!!\nPer te dal nga loja shkruani 'exit' \nJu lutem shtypni nje numer. \nKarakteret e lejuara jane:\n1,2,3,4,5,6,7,8,9,0 \nNe rangun 1-36.");
                
            }
        }
        System.out.println("Numrat qe keni zgjedhur jane: ");
        printArray(userNumbers);
    }// merr hyrje nga shfrytezuesi ne menyre interaktive.
    
    public boolean checkRpt(int[] vrg, int nr) {
        boolean result = true;
        for (int j = 0; j < vrg.length; j++) {
            if (nr == vrg[j]) {
                result = false;
            }
        }
        return result;
    }//Kontrollon hyrjet e numrave dhe nuk lejon qe te perseriten.

    private void randomNumbers() {
        for (int i = 0; i < TOTAL_NUM; i++) {
            ranNumber = (int) (Math.random() * (36) + 1);
            boolean checkRanRpt = checkRanRpt(lottoNumbers, ranNumber);
            if (checkRanRpt == false) {
                i--;
            } else {
                lottoNumbers[i] = ranNumber;
            }
        }
        printArray(lottoNumbers);
    }//gjeneron numra te zakonshem ne rangun prej 1 deri 36.

    public boolean checkRanRpt(int[] vrg, int nr) {
        boolean result = true;
        for (int j = 0; j < vrg.length; j++) {
            if (nr == vrg[j]) {
                result = false;
            }
        }
        return result;
    }//Kontrollon gjenerimin kompjuterik te numrave dhe nuk lejon qe te perseriten.

    public int getNumMatches(int[] guesses, int[] key) {
        int numMatches = 0;
        for (int i = 0; i < guesses.length; i++) {
            for (int j = 0; j < key.length; j++) {
                if (guesses[i] == key[j]) {
                    numMatches++;
                }
            }
        }
        if (numMatches > 0) {
            if (numMatches > 1) {
                System.out.println("\nUrime. Keni qelluar " + numMatches + " numra.");
            } else {
                System.out.println("\nUrime. Keni qelluar " + numMatches + " numer.");
            }
        } else {
            System.out.println("\nFatkeqsisht nuk keni qelluar asnje numer. Provoni perseri!");
        }
        return numMatches;
    } //llogarit sa numra ka qelluar lojtari

    public static void printArray(int[] list) {
        String rezultati = "";
        for (int i = 0; i < list.length; i++) {
            System.out.print(" " + list[i]);
            rezultati = rezultati + " " + list[i];
        }
    }//afishon vargun e numrave qe i kerkohet (ne rastin tone kemi dy vargje dhe afishon ate qe i kerkohet.)

    public void printReport() {
        //Thirret metoda e cila gjeneron hyrje nga shfrytezuesi
        inputData();
        //Afishon shfrytezuesit disa informata te pergjithshme.
        System.out.println("\nNumrat fitues te lotarise jane: ");
        //Thirret metoda e cila gjeneron dhe afishon numra te zakonshem te llotarise.
        randomNumbers();
        //removeRan(ranNumber);
        getNumMatches(userNumbers, lottoNumbers);
    }//Afishon raportin ose te gjitha te dhenat e nevojshme shfrytezuesit.

    public static void main(String[] args) {
        Lottary6from36 l636 = new Lottary6from36();
        l636.printReport();
    }// Metoda main per ekzekutim.
}
