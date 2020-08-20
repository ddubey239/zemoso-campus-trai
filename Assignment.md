#week1 Assignment
import edu.duke.*;
import java.io.File;
/**
 * Write a description of Part1 here.
 * 
 * @author (your name) 
 * @version (a version number or a date)
 */
public class Part1 {
    public String findSimpleGene(String dna) {
        int startIndex = dna.indexOf("ATG");
        if(startIndex==-1) {
            return "";
        }
        int endIndex = dna.indexOf("TAA");
        if(endIndex==-1) {
            return "";
        }
        if((endIndex-startIndex)%3==0){
            return dna.substring(startIndex, endIndex+3);
        }
        else return "";
    }
    
    void testSimpleGene() {
        String dna = "AATGCGTAATATGCT";
        System.out.println("DNA strand is "+dna);
        System.out.println("Gene is "+findSimpleGene(dna));
        dna = "AATGCTAGGGTAATATGGT";
        System.out.println("DNA strand is "+dna);
        System.out.println("Gene is "+findSimpleGene(dna));
        dna = "ATCCTATAA";
        System.out.println("DNA strand is "+dna);
        System.out.println("Gene is "+findSimpleGene(dna));
        dna  = "TCATGCBDKLP";
        System.out.println("DNA strand is "+dna);
        System.out.println("Gene is "+findSimpleGene(dna));
        dna  = "DFGHJTYUIO";
        System.out.println("DNA strand is "+dna);
        System.out.println("Gene is "+findSimpleGene(dna));
    }
    
    public static void main(String[] args) {
        Part1 obj = new Part1();
        obj.testSimpleGene();
    }
}
