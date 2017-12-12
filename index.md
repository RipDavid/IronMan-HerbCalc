import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

public class HerbloreCalc extends JPanel {
    static int[] herblore = new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0};

    private JPanel IntroPanel;
    private JPanel ResultPanel;
    private JPanel BodyPanel;
    private JPanel CurrentLvlPannel;

    private  JTextField CurrentLvlInput = new JTextField(5);

    private JTextField GuamInput = new JTextField(5);
    private JTextField TarrominInput = new JTextField(5);
    private JTextField HarrlanderInput = new JTextField(5);
    private JTextField RannarInput = new JTextField(5);
    private JTextField IritInput = new JTextField(5);
    private JTextField AvantoeInput = new JTextField(5);
    private JTextField KwuarmInput = new JTextField(5);
    private JTextField SnapDragonInput = new JTextField(5);
    private JTextField CadantineInput = new JTextField(5);
    private JTextField LantadymeInput = new JTextField(5);
    private JTextField DwarfWeedInput = new JTextField(5);
    private JTextField ToadFalxInput = new JTextField(5);
    private JTextField SuperCombatInput = new JTextField(5);

    private JTextField CombatPotInput = new JTextField(5);
    private JTextField AntiFireInput = new JTextField(5);
    private JTextField ExtenedAntiFireInput = new JTextField(5);
    private JTextField StaminaInput = new JTextField(5);
    private JTextField AntiVenomInput = new JTextField(5);
    private JTextField AntiVemonPlusInput =new JTextField(5);

    private JButton TotalXpButton = new JButton("     Calculate the Total Herblore xp You Have     ");
    private JLabel Label1 = new JLabel("Enter The Number of Each Clean Herb You Have Below:        ");
    private JLabel Label2 = new JLabel("Leave a 0 if Your Not Planning On Using That Herb Or Have None");
    private JLabel BlankLabel1 = new JLabel("\n");
    private JLabel BlankLabel2 = new JLabel("\n");
    private JLabel MiscLabel =new JLabel("Miscellaneous/Other Potions");
    private JLabel BlankLabel3 =new JLabel("\n");

    private JLabel CurrentLvlTextLabel = new JLabel("Enter your Current Xp");

    private JLabel GuamTextLabel = new JLabel("(Attack Pots) Enter Guam Amount: ");
    private JLabel TarrominTextLabel = new JLabel("(Strength/Serum207 Pots) Enter Tarromin Amount: ");
    private JLabel HarralanderTextLabel = new JLabel("(Energy Pots) Enter Harralander Amount: ");
    private JLabel RanarrTextLabel = new JLabel("(Prayer Pots) Enter Rannar Amount: ");
    private JLabel IritTextLabel = new JLabel("(Super Attack Pots) Enter Irit Amount: ");
    private JLabel AvantoeTextLabel = new JLabel("(Super Energy Pots) Enter Avantoe Amount: ");
    private JLabel KwuarmTextLabel = new JLabel("(Super Strength Pots) Enter Kwuarm Amount: ");
    private JLabel SnapDragonTextLabel = new JLabel("(Super Restore Pots) Enter Snapdragon Amount: ");
    private JLabel CadantineTextLabel = new JLabel("(Super Defence Pots) Enter Cadantine Amount: ");
    private JLabel LantadymeTextLabel = new JLabel("(Magic Pots) Enter Lantadyme Amount: ");
    private JLabel DwarfWeedTextLabel = new JLabel("(Ranging Pots) Enter Dwarfweed Amount: ");
    private JLabel ToadFlaxTextLabel = new JLabel("(Saradomin Brews) Enter Toadflax Amount: ");
    private JLabel SuperCombatTextLabel = new JLabel("(Super Combat Pot) Enter Torstol Amount: ");

    private JLabel CombatPotLabel= new JLabel("(Combat Pot) Enter Harralander Amount: ");
    private JLabel AntifireTextLabel = new JLabel("(Anti-fire) Enter Lantadyme Amount: ");
    private JLabel ExtenedAntifireTextLabel = new JLabel("(Extended Anti-fires) Enter Anti-fire (4) Amount: ");
    private JLabel StaminaTextLabel = new JLabel("(Stamina Pots) Enter Super Energy (4) Amount: ");
    private JLabel AntiVenomTextLabel = new JLabel("(Anti-Vemon) Enter Antidote Amount: ");
    private JLabel AntiVemonPlusTextLabel = new JLabel("AntiV-Vemon +) Enter Anti-Vemon Amount: ");

    private JLabel TotalHerbXp = new JLabel("Available Herblore Xp Is: Not Available ");
    private JLabel HerbLvl = new JLabel("Current Herblore Lvl Is: 1 ");
    private JLabel AnticipatedHerbLvlLabel =new JLabel("Anticipated Herblore Lvl Is: Not Available");

    public HerbloreCalc() {
        // Layout of interface
        this.setPreferredSize(new Dimension(600, 535));
        this.setBackground(new Color(255, 255, 255));

        //Setting all inputs to 0
        CurrentLvlInput.setText("0");
        GuamInput.setText("0");
        TarrominInput.setText("0");
        HarrlanderInput.setText("0");
        RannarInput.setText("0");
        IritInput.setText("0");
        AvantoeInput.setText("0");
        KwuarmInput.setText("0");
        SnapDragonInput.setText("0");
        CadantineInput.setText("0");
        LantadymeInput.setText("0");
        DwarfWeedInput.setText("0");
        ToadFalxInput.setText("0");
        SuperCombatInput.setText("0");

        CombatPotInput.setText("0");
        AntiFireInput.setText("0");
        ExtenedAntiFireInput.setText("0");
        StaminaInput.setText("0");
        AntiVenomInput.setText("0");
        AntiVemonPlusInput.setText("0");


        IntroPanel= new JPanel(new GridLayout(2,1));
        CurrentLvlPannel =new JPanel(new GridLayout(2,1));
        ResultPanel=new JPanel(new GridLayout(2,2));
        BodyPanel=new JPanel(new GridLayout(21,2));

        this.TotalXpButton.addActionListener(new totalHerblButtonListener());

        IntroPanel.add(this.Label1);
        IntroPanel.add(this.Label2);
        add(IntroPanel);

        CurrentLvlPannel.add(this.CurrentLvlTextLabel);
        CurrentLvlPannel.add(this.CurrentLvlInput);
        add(CurrentLvlPannel);

        BodyPanel.add(this.GuamTextLabel);
        BodyPanel.add(this.GuamInput);
        BodyPanel.add(this.TarrominTextLabel);
        BodyPanel.add(this.TarrominInput);
        BodyPanel.add(this.HarralanderTextLabel);
        BodyPanel.add(this.HarrlanderInput);
        BodyPanel.add(this.RanarrTextLabel);
        BodyPanel.add(this.RannarInput);
        BodyPanel.add(this.IritTextLabel);
        BodyPanel.add(this.IritInput);
        BodyPanel.add(this.AvantoeTextLabel);
        BodyPanel.add(this.AvantoeInput);
        BodyPanel.add(this.KwuarmTextLabel);
        BodyPanel.add(this.KwuarmInput);
        BodyPanel.add(this.SnapDragonTextLabel);
        BodyPanel.add(this.SnapDragonInput);
        BodyPanel.add(this.CadantineTextLabel);
        BodyPanel.add(this.CadantineInput);
        BodyPanel.add(this.LantadymeTextLabel);
        BodyPanel.add(this.LantadymeInput);
        BodyPanel.add(this.DwarfWeedTextLabel);
        BodyPanel.add(this.DwarfWeedInput);
        BodyPanel.add(this.ToadFlaxTextLabel);
        BodyPanel.add(this.ToadFalxInput);
        BodyPanel.add(this.SuperCombatTextLabel);
        BodyPanel.add(this.SuperCombatInput);

        BodyPanel.add(this.BlankLabel1);
        BodyPanel.add(this.BlankLabel2);
        BodyPanel.add(this.MiscLabel);
        BodyPanel.add(this.BlankLabel3);

        BodyPanel.add(this.CombatPotLabel);
        BodyPanel.add(this.CombatPotInput);
        BodyPanel.add(this.AntifireTextLabel);
        BodyPanel.add(this.AntiFireInput);
        BodyPanel.add(ExtenedAntifireTextLabel);
        BodyPanel.add(ExtenedAntiFireInput);
        BodyPanel.add(StaminaTextLabel);
        BodyPanel.add(StaminaInput);
        BodyPanel.add(AntiVenomTextLabel);
        BodyPanel.add(AntiVenomInput);
        BodyPanel.add(AntiVemonPlusTextLabel);
        BodyPanel.add(AntiVemonPlusInput);

        add(BodyPanel);

        ResultPanel.add(this.HerbLvl);
        ResultPanel.add(this.TotalXpButton);
        ResultPanel.add(this.AnticipatedHerbLvlLabel);
        ResultPanel.add(this.TotalHerbXp);
        add(ResultPanel);

    }


    //(Calc) Each potion and its xp here
    private int totalHerbCompute() {
        return (int) ((herblore[0] * 25) + (herblore[1] * 50) + (herblore[2] * 67.5) + (herblore[3] * 87.5) + (herblore[4] * 100) +
                (herblore[5] * 117.5) + (herblore[6] * 125) + (herblore[7] * 142.5) + (herblore[8] * 150) + (herblore[9] * 172.5) +
                (herblore[10] * 162.5) + (herblore[11] * 180) + (herblore[12] * 150) + (herblore[13] * 157.5) + (herblore[14] * 110)
                + (herblore[15] * 102) + (herblore[16] * 120) + (herblore[17] * 125) + (herblore[18] * 84)
        );
    }


    // Users xp input to return their lvl
    private int HerbLvL() {
        int herbxp = herblore[19];

        // Exp for each lvl

        if (herbxp >= 0 && herbxp <=82)
            {
             return 1;
            }
        else if (herbxp>=83 && herbxp<=173)
        {
            return 2;
        }
        else if (herbxp>=174 && herbxp<=275)
        {
            return 3;
        }
        else if (herbxp>=276 && herbxp<=386)
        {
            return 4;
        }
        else if (herbxp>=387 && herbxp<=511)
        {
            return 5;
        }
        else if (herbxp>=512 && herbxp<=649)
        {
            return 6;
        }
        else if (herbxp>=650 && herbxp<=800)
        {
            return 7;
        }
        else if (herbxp>=801 && herbxp<=968)
        {
            return 8;
        }
        else if (herbxp>=969 && herbxp<=1153)
        {
            return 9;
        }
        else if (herbxp>=1154 && herbxp<=1357)
        {
            return 10;
        }
        else if (herbxp>=1358 && herbxp<=1583)
        {
            return 11;
        }
        else if (herbxp>=1584 && herbxp<=1832)
        {
            return 12;
        }
        else if (herbxp>=1833 && herbxp<=2106)
        {
            return 13;
        }
        else if (herbxp>=2107 && herbxp<=2410)
        {
            return 14;
        }
        else if (herbxp>=2411 && herbxp<=2745)
        {
            return 15;
        }
        else if (herbxp>=2746 && herbxp<=3114)
        {
            return 16;
        }
        else if (herbxp>=3115 && herbxp<=3522)
        {
            return 17;
        }
        else if (herbxp>=3523 && herbxp<=3972)
        {
            return 18;
        }
        else if (herbxp>=3973 && herbxp<=4469)
        {
            return 19;
        }
        else if (herbxp>=4470 && herbxp<=5017)
        {
            return 20;
        }
        else if (herbxp>=5018 && herbxp<=5623)
        {
            return 21;
        }
        else if (herbxp>=5624 && herbxp<=6290)
        {
            return 22;
        }
        else if (herbxp>=6291 && herbxp<=7027)
        {
            return 23;
        }
        else if (herbxp>=7028 && herbxp<=7841)
        {
            return 24;
        }
        else if (herbxp>=7842 && herbxp<=8739)
        {
            return 25;
        }
        else if (herbxp>=8740 && herbxp<=9729)
        {
            return 26;
        }
        else if (herbxp>=9730 && herbxp<=10823)
        {
            return 27;
        }
        else if (herbxp>=10824 && herbxp<=12030)
        {
            return 28;
        }
        else if (herbxp>=12031 && herbxp<=13362)
        {
            return 29;
        }
        else if (herbxp>=13363 && herbxp<=14832)
        {
            return 30;
        }
        else if (herbxp>=14833 && herbxp<=16455)
        {
            return 31;
        }
        else if (herbxp>=16456 && herbxp<=18246)
        {
            return 32;
        }
        else if (herbxp>=18247 && herbxp<=20223)
        {
            return 33;
        }
        else if (herbxp>=20224 && herbxp<=22405)
        {
            return 34;
        }
        else if (herbxp>=22406 && herbxp<=24814)
        {
            return 35;
        }
        else if (herbxp>=24815 && herbxp<=27472)
        {
            return 36;
        }
        else if (herbxp>=27473 && herbxp<=30407)
        {
            return 37;
        }
        else if (herbxp>=30408 && herbxp<=33647)
        {
            return 38;
        }
        else if (herbxp>=33648 && herbxp<=37223)
        {
            return 39;
        }
        else if (herbxp>=37224 && herbxp<=41170)
        {
            return 40;
        }
        else if (herbxp>=41171 && herbxp<=45528)
        {
            return 41;
        }
        else if (herbxp>=45529 && herbxp<=50338)
        {
            return 42;
        }
        else if (herbxp>=50339 && herbxp<=55648)
        {
            return 43;
        }
        else if (herbxp>=55649 && herbxp<=61511)
        {
            return 44;
        }
        else if (herbxp>=61512 && herbxp<=67982)
        {
            return 45;
        }
        else if (herbxp>=67983 && herbxp<=75126)
        {
            return 46;
        }
        else if (herbxp>=75127 && herbxp<=83013)
        {
            return 47;
        }
        else if (herbxp>=83014 && herbxp<=91720)
        {
            return 48;
        }
        else if (herbxp>=91721 && herbxp<=101332)
        {
            return 49;
        }
        else if (herbxp>=101333 && herbxp<=111944)
        {
            return 50;
        }
        else if (herbxp>=111945 && herbxp<=123659)
        {
            return 51;
        }
        else if (herbxp>=123660 && herbxp<=136593)
        {
            return 52;
        }
        else if (herbxp>=136594 && herbxp<=150871)
        {
            return 53;
        }
        else if (herbxp>=150872 && herbxp<=166635)
        {
            return 54;
        }
        else if (herbxp>=166636 && herbxp<=184039)
        {
            return 55;
        }
        else if (herbxp>=184040 && herbxp<=203253)
        {
            return 56;
        }
        else if (herbxp>=203254 && herbxp<=224465)
        {
            return 57;
        }
        else if (herbxp>=224466 && herbxp<=247885)
        {
            return 58;
        }
        else if (herbxp>=247886 && herbxp<=273741)
        {
            return 59;
        }
        else if (herbxp>=273742 && herbxp<=302287)
        {
            return 60;
        }
        else if (herbxp>=302288 && herbxp<=333803)
        {
            return 61;
        }
        else if (herbxp>=333804 && herbxp<=368598)
        {
            return 62;
        }
        else if (herbxp>=368599 && herbxp<=407014)
        {
            return 63;
        }
        else if (herbxp>=407015 && herbxp<=449427)
        {
            return 64;
        }
        else if (herbxp>=449428 && herbxp<=496253)
        {
            return 65;
        }
        else if (herbxp>=496254 && herbxp<=547952)
        {
            return 66;
        }
        else if (herbxp>=547953 && herbxp<=605031)
        {
            return 67;
        }
        else if (herbxp>=605032 && herbxp<=668050)
        {
            return 68;
        }
        else if (herbxp>=668051 && herbxp<=737626)
        {
            return 69;
        }
        else if (herbxp>=737627 && herbxp<=814444)
        {
            return 70;
        }
        else if (herbxp>=814445 && herbxp<=899256)
        {
            return 71;
        }
        else if (herbxp>=899257 && herbxp<=992894)
        {
            return 72;
        }
        else if (herbxp>=992895 && herbxp<=1096277)
        {
            return 73;
        }
        else if (herbxp>=1096278 && herbxp<=1210420)
        {
            return 74;
        }
        else if (herbxp>=1210421 && herbxp<=1336442)
        {
            return 75;
        }
        else if (herbxp>=1336443 && herbxp<=1475580)
        {
            return 76;
        }
        else if (herbxp>=1475581 && herbxp<=1629199)
        {
            return 77;
        }
        else if (herbxp>=1629200 && herbxp<=1798807)
        {
            return 78;
        }
        else if (herbxp>=1798808 && herbxp<=1986067)
        {
            return 79;
        }
        else if (herbxp>=1986068 && herbxp<=2192817)
        {
            return 80;
        }
        else if (herbxp>=2192818 && herbxp<=2421086)
        {
            return 81;
        }
        else if (herbxp>=2421087 && herbxp<=2673113)
        {
            return 82;
        }
        else if (herbxp>=2673114 && herbxp<=2951372)
        {
            return 83;
        }
        else if (herbxp>=2951373 && herbxp<=3258593)
        {
            return 84;
        }
        else if (herbxp>=3258594 && herbxp<=3597791)
        {
            return 85;
        }
        else if (herbxp>=3597792 && herbxp<=3972293)
        {
            return 86;
        }
        else if (herbxp>=3972294 && herbxp<=4385775)
        {
            return 87;
        }
        else if (herbxp>=4385776 && herbxp<=4842294)
        {
            return 88;
        }
        else if (herbxp>=4842295 && herbxp<=5346331)
        {
            return 89;
        }
        else if (herbxp>=5346332 && herbxp<=5902830)
        {
            return 90;
        }
        else if (herbxp>=5902831 && herbxp<=6517252)
        {
            return 91;
        }
        else if (herbxp>=6517253 && herbxp<=7195628)
        {
            return 92;
        }
        else if (herbxp>=7195629 && herbxp<=7944613)
        {
            return 93;
        }
        else if (herbxp>=7944614 && herbxp<=8771557)
        {
            return 94;
        }
        else if (herbxp>=8771558 && herbxp<=9684576)
        {
            return 95;
        }
        else if (herbxp>=9684577 && herbxp<=10692628)
        {
            return 96;
        }
        else if (herbxp>=10692629 && herbxp<=11805605)
        {
            return 97;
        }
        else if (herbxp>=11805606 && herbxp<=13034430)
        {
            return 98;
        }
        else if (herbxp>=13034431)
        {
            return 99;
        }
        else if (herbxp>13034431)
        {
            return 99;
        }
        else
        {
            return 0;
        }
    }

    // Users xp input + the xp available to give predicted lvl
    private  int AnticipatedLvl (){
        int AnticipatedXp = herblore [19] + totalHerbCompute();

        //Exp for each Herb lvl
        if (AnticipatedXp >= 0 && AnticipatedXp <=82)
        {
            return 1;
        }
        else if (AnticipatedXp>=83 && AnticipatedXp<=173)
        {
            return 2;
        }
        else if (AnticipatedXp>=174 && AnticipatedXp<=275)
        {
            return 3;
        }
        else if (AnticipatedXp>=276 && AnticipatedXp<=386)
        {
            return 4;
        }
        else if (AnticipatedXp>=387 && AnticipatedXp<=511)
        {
            return 5;
        }
        else if (AnticipatedXp>=512 && AnticipatedXp<=649)
        {
            return 6;
        }
        else if (AnticipatedXp>=650 && AnticipatedXp<=800)
        {
            return 7;
        }
        else if (AnticipatedXp>=801 && AnticipatedXp<=968)
        {
            return 8;
        }
        else if (AnticipatedXp>=969 && AnticipatedXp<=1153)
        {
            return 9;
        }
        else if (AnticipatedXp>=1154 && AnticipatedXp<=1357)
        {
            return 10;
        }
        else if (AnticipatedXp>=1358 && AnticipatedXp<=1583)
        {
            return 11;
        }
        else if (AnticipatedXp>=1584 && AnticipatedXp<=1832)
        {
            return 12;
        }
        else if (AnticipatedXp>=1833 && AnticipatedXp<=2106)
        {
            return 13;
        }
        else if (AnticipatedXp>=2107 && AnticipatedXp<=2410)
        {
            return 14;
        }
        else if (AnticipatedXp>=2411 && AnticipatedXp<=2745)
        {
            return 15;
        }
        else if (AnticipatedXp>=2746 && AnticipatedXp<=3114)
        {
            return 16;
        }
        else if (AnticipatedXp>=3115 && AnticipatedXp<=3522)
        {
            return 17;
        }
        else if (AnticipatedXp>=3523 && AnticipatedXp<=3972)
        {
            return 18;
        }
        else if (AnticipatedXp>=3973 && AnticipatedXp<=4469)
        {
            return 19;
        }
        else if (AnticipatedXp>=4470 && AnticipatedXp<=5017)
        {
            return 20;
        }
        else if (AnticipatedXp>=5018 && AnticipatedXp<=5623)
        {
            return 21;
        }
        else if (AnticipatedXp>=5624 && AnticipatedXp<=6290)
        {
            return 22;
        }
        else if (AnticipatedXp>=6291 && AnticipatedXp<=7027)
        {
            return 23;
        }
        else if (AnticipatedXp>=7028 && AnticipatedXp<=7841)
        {
            return 24;
        }
        else if (AnticipatedXp>=7842 && AnticipatedXp<=8739)
        {
            return 25;
        }
        else if (AnticipatedXp>=8740 && AnticipatedXp<=9729)
        {
            return 26;
        }
        else if (AnticipatedXp>=9730 && AnticipatedXp<=10823)
        {
            return 27;
        }
        else if (AnticipatedXp>=10824 && AnticipatedXp<=12030)
        {
            return 28;
        }
        else if (AnticipatedXp>=12031 && AnticipatedXp<=13362)
        {
            return 29;
        }
        else if (AnticipatedXp>=13363 && AnticipatedXp<=14832)
        {
            return 30;
        }
        else if (AnticipatedXp>=14833 && AnticipatedXp<=16455)
        {
            return 31;
        }
        else if (AnticipatedXp>=16456 && AnticipatedXp<=18246)
        {
            return 32;
        }
        else if (AnticipatedXp>=18247 && AnticipatedXp<=20223)
        {
            return 33;
        }
        else if (AnticipatedXp>=20224 && AnticipatedXp<=22405)
        {
            return 34;
        }
        else if (AnticipatedXp>=22406 && AnticipatedXp<=24814)
        {
            return 35;
        }
        else if (AnticipatedXp>=24815 && AnticipatedXp<=27472)
        {
            return 36;
        }
        else if (AnticipatedXp>=27473 && AnticipatedXp<=30407)
        {
            return 37;
        }
        else if (AnticipatedXp>=30408 && AnticipatedXp<=33647)
        {
            return 38;
        }
        else if (AnticipatedXp>=33648 && AnticipatedXp<=37223)
        {
            return 39;
        }
        else if (AnticipatedXp>=37224 && AnticipatedXp<=41170)
        {
            return 40;
        }
        else if (AnticipatedXp>=41171 && AnticipatedXp<=45528)
        {
            return 41;
        }
        else if (AnticipatedXp>=45529 && AnticipatedXp<=50338)
        {
            return 42;
        }
        else if (AnticipatedXp>=50339 && AnticipatedXp<=55648)
        {
            return 43;
        }
        else if (AnticipatedXp>=55649 && AnticipatedXp<=61511)
        {
            return 44;
        }
        else if (AnticipatedXp>=61512 && AnticipatedXp<=67982)
        {
            return 45;
        }
        else if (AnticipatedXp>=67983 && AnticipatedXp<=75126)
        {
            return 46;
        }
        else if (AnticipatedXp>=75127 && AnticipatedXp<=83013)
        {
            return 47;
        }
        else if (AnticipatedXp>=83014 && AnticipatedXp<=91720)
        {
            return 48;
        }
        else if (AnticipatedXp>=91721 && AnticipatedXp<=101332)
        {
            return 49;
        }
        else if (AnticipatedXp>=101333 && AnticipatedXp<=111944)
        {
            return 50;
        }
        else if (AnticipatedXp>=111945 && AnticipatedXp<=123659)
        {
            return 51;
        }
        else if (AnticipatedXp>=123660 && AnticipatedXp<=136593)
        {
            return 52;
        }
        else if (AnticipatedXp>=136594 && AnticipatedXp<=150871)
        {
            return 53;
        }
        else if (AnticipatedXp>=150872 && AnticipatedXp<=166635)
        {
            return 54;
        }
        else if (AnticipatedXp>=166636 && AnticipatedXp<=184039)
        {
            return 55;
        }
        else if (AnticipatedXp>=184040 && AnticipatedXp<=203253)
        {
            return 56;
        }
        else if (AnticipatedXp>=203254 && AnticipatedXp<=224465)
        {
            return 57;
        }
        else if (AnticipatedXp>=224466 && AnticipatedXp<=247885)
        {
            return 58;
        }
        else if (AnticipatedXp>=247886 && AnticipatedXp<=273741)
        {
            return 59;
        }
        else if (AnticipatedXp>=273742 && AnticipatedXp<=302287)
        {
            return 60;
        }
        else if (AnticipatedXp>=302288 && AnticipatedXp<=333803)
        {
            return 61;
        }
        else if (AnticipatedXp>=333804 && AnticipatedXp<=368598)
        {
            return 62;
        }
        else if (AnticipatedXp>=368599 && AnticipatedXp<=407014)
        {
            return 63;
        }
        else if (AnticipatedXp>=407015 && AnticipatedXp<=449427)
        {
            return 64;
        }
        else if (AnticipatedXp>=449428 && AnticipatedXp<=496253)
        {
            return 65;
        }
        else if (AnticipatedXp>=496254 && AnticipatedXp<=547952)
        {
            return 66;
        }
        else if (AnticipatedXp>=547953 && AnticipatedXp<=605031)
        {
            return 67;
        }
        else if (AnticipatedXp>=605032 && AnticipatedXp<=668050)
        {
            return 68;
        }
        else if (AnticipatedXp>=668051 && AnticipatedXp<=737626)
        {
            return 69;
        }
        else if (AnticipatedXp>=737627 && AnticipatedXp<=814444)
        {
            return 70;
        }
        else if (AnticipatedXp>=814445 && AnticipatedXp<=899256)
        {
            return 71;
        }
        else if (AnticipatedXp>=899257 && AnticipatedXp<=992894)
        {
            return 72;
        }
        else if (AnticipatedXp>=992895 && AnticipatedXp<=1096277)
        {
            return 73;
        }
        else if (AnticipatedXp>=1096278 && AnticipatedXp<=1210420)
        {
            return 74;
        }
        else if (AnticipatedXp>=1210421 && AnticipatedXp<=1336442)
        {
            return 75;
        }
        else if (AnticipatedXp>=1336443 && AnticipatedXp<=1475580)
        {
            return 76;
        }
        else if (AnticipatedXp>=1475581 && AnticipatedXp<=1629199)
        {
            return 77;
        }
        else if (AnticipatedXp>=1629200 && AnticipatedXp<=1798807)
        {
            return 78;
        }
        else if (AnticipatedXp>=1798808 && AnticipatedXp<=1986067)
        {
            return 79;
        }
        else if (AnticipatedXp>=1986068 && AnticipatedXp<=2192817)
        {
            return 80;
        }
        else if (AnticipatedXp>=2192818 && AnticipatedXp<=2421086)
        {
            return 81;
        }
        else if (AnticipatedXp>=2421087 && AnticipatedXp<=2673113)
        {
            return 82;
        }
        else if (AnticipatedXp>=2673114 && AnticipatedXp<=2951372)
        {
            return 83;
        }
        else if (AnticipatedXp>=2951373 && AnticipatedXp<=3258593)
        {
            return 84;
        }
        else if (AnticipatedXp>=3258594 && AnticipatedXp<=3597791)
        {
            return 85;
        }
        else if (AnticipatedXp>=3597792 && AnticipatedXp<=3972293)
        {
            return 86;
        }
        else if (AnticipatedXp>=3972294 && AnticipatedXp<=4385775)
        {
            return 87;
        }
        else if (AnticipatedXp>=4385776 && AnticipatedXp<=4842294)
        {
            return 88;
        }
        else if (AnticipatedXp>=4842295 && AnticipatedXp<=5346331)
        {
            return 89;
        }
        else if (AnticipatedXp>=5346332 && AnticipatedXp<=5902830)
        {
            return 90;
        }
        else if (AnticipatedXp>=5902831 && AnticipatedXp<=6517252)
        {
            return 91;
        }
        else if (AnticipatedXp>=6517253 && AnticipatedXp<=7195628)
        {
            return 92;
        }
        else if (AnticipatedXp>=7195629 && AnticipatedXp<=7944613)
        {
            return 93;
        }
        else if (AnticipatedXp>=7944614 && AnticipatedXp<=8771557)
        {
            return 94;
        }
        else if (AnticipatedXp>=8771558 && AnticipatedXp<=9684576)
        {
            return 95;
        }
        else if (AnticipatedXp>=9684577 && AnticipatedXp<=10692628)
        {
            return 96;
        }
        else if (AnticipatedXp>=10692629 && AnticipatedXp<=11805605)
        {
            return 97;
        }
        else if (AnticipatedXp>=11805606 && AnticipatedXp<=13034430)
        {
            return 98;
        }
        else if (AnticipatedXp>=13034431)
        {
            return 99;
        }
        else if (AnticipatedXp>13034431)
        {
            return 99;
        }
        else
        {
            return 0;
        }
    }



    private class totalHerblButtonListener implements ActionListener {
        private totalHerblButtonListener() {
        }

        public void actionPerformed(ActionEvent event) {
            //takes Users inputs and enters into formula
            HerbloreCalc.herblore[0] = Integer.parseInt(HerbloreCalc.this.GuamInput.getText());
            HerbloreCalc.herblore[1] = Integer.parseInt(HerbloreCalc.this.TarrominInput.getText());
            HerbloreCalc.herblore[2] = Integer.parseInt(HerbloreCalc.this.HarrlanderInput.getText());
            HerbloreCalc.herblore[3] = Integer.parseInt(HerbloreCalc.this.RannarInput.getText());
            HerbloreCalc.herblore[4] = Integer.parseInt(HerbloreCalc.this.IritInput.getText());
            HerbloreCalc.herblore[5] = Integer.parseInt(HerbloreCalc.this.AvantoeInput.getText());
            HerbloreCalc.herblore[6] = Integer.parseInt(HerbloreCalc.this.KwuarmInput.getText());
            HerbloreCalc.herblore[7] = Integer.parseInt(HerbloreCalc.this.SnapDragonInput.getText());
            HerbloreCalc.herblore[8] = Integer.parseInt(HerbloreCalc.this.CadantineInput.getText());
            HerbloreCalc.herblore[9] = Integer.parseInt(HerbloreCalc.this.LantadymeInput.getText());
            HerbloreCalc.herblore[10] = Integer.parseInt(HerbloreCalc.this.DwarfWeedInput.getText());
            HerbloreCalc.herblore[11] = Integer.parseInt(HerbloreCalc.this.ToadFalxInput.getText());
            HerbloreCalc.herblore[12] = Integer.parseInt(HerbloreCalc.this.SuperCombatInput.getText());
            HerbloreCalc.herblore[13] = Integer.parseInt(HerbloreCalc.this.AntiFireInput.getText());
            HerbloreCalc.herblore[14] = Integer.parseInt(HerbloreCalc.this.ExtenedAntiFireInput.getText());
            HerbloreCalc.herblore[15] = Integer.parseInt(HerbloreCalc.this.StaminaInput.getText());
            HerbloreCalc.herblore[16] = Integer.parseInt(HerbloreCalc.this.AntiVenomInput.getText());
            HerbloreCalc.herblore[17] = Integer.parseInt(HerbloreCalc.this.AntiVemonPlusInput.getText());
            HerbloreCalc.herblore[18] = Integer.parseInt(HerbloreCalc.this.CombatPotInput.getText());

            HerbloreCalc.herblore[19] = Integer.parseInt(HerbloreCalc.this.CurrentLvlInput.getText());


            //Results
            HerbloreCalc.this.TotalHerbXp.setText("The Available Herblore Xp You Have Is: " + HerbloreCalc.this.totalHerbCompute());
            HerbloreCalc.this.HerbLvl.setText("Your Current Herblore Lvl Is: " + HerbloreCalc.this.HerbLvL());
            HerbloreCalc.this.AnticipatedHerbLvlLabel.setText("Your Anticipated Herblore Lvl Is: " + HerbloreCalc.this.AnticipatedLvl());
        }
    }
}
