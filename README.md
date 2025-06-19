# Neumann_Seminararbeit_R
Repository for R Code
rm(list =ls())

library(kableExtra)


player = c("Novak Djokovic", "Dino Prizmic", "Alexei Popyrin", "Marc Polmans", "Yannick Hanfmann",
           "Gael Monfils", "Andy Murray", "Tomas Martin Etcheverry", "Adrian Mannarino", "Stan Wawrinka",
           "Alexander Shevchenko", "Jaume Munar", "Christopher O'Connell", "Christian Garin",
           "Roberto Bautista Agut", "Ben Shelton", "Taylor Fritz", "Facundo Diaz Acosta",
           "Roberto Carballes Baena", "Hugo Gaston", "Fabian Marozsan", "Marin Cilic", "Dane Sweeny",
           "Francisco Cerundolo", "Lorenzo Musetti", "Benjamin Bonzi", "James Duckworth", "Luca Van Assche",
           "Aleksandar Vukic", "Jordan Thompson", "Zizou Bergs", "Stefanos Tsitsipas", "Jannik Sinner",
           "Botic Van de Zandschulp", "Jesper de Jong", "Pedro Cachin", "Daniel Elahi Galan", "Jason Kubler",
           "Jeffrey John Wolf", "Sebastian Baez", "Frances Tiafoe", "Borna Coric", "Tomas Machac",
           "Shintaro Mochizuki", "Alejandro Tabilo", "Aleksandar Kovacevic", "Daniel Altmaier",
           "Karen Khachanov", "Alex De Minaur", "Milos Raonic", "Matteo Arnaldi", "Adam Walton", "Pavel Kotov",
           "Arthur Rinderknech", "Flavio Cobolli", "Nicolas Jarry", "Sebastian Korda", "Vit Kopriva", "Quentin Halys",
           "Lloyd Harris", "Chris Eubanks", "Taro Daniel", "Thiago Seyboth Wild", "Andrey Rublev", "Hoger Rune",
           "Yoshihito Nishioka", "Laslo Djere", "Arthur Cazaux", "Arthur Fils", "Jiri Vesely", "Roman Safiullin",
           "Tallon Griekspoor", "Ugo Humbert", "David Goffin", "Zhang Zhizhen", "Federico Coria", "Denis Shapovalov",
           "Jakub Mensik", "Omar Jasika", "Hubert Hurkacz", "Grigor Dimitrov", "Marton Fucsovics", "Sebastian Ofner",
           "Thanasi Kokkinakis", "Maximilian Marterer", "Nuno Borges", "Constant Lestienne",
           "Alejandro Davidovich Fokina", "Felix Auger-Aliassime", "Dominic Thiem", "Alexandre Mueller",
           "Hugo Grenier", "Patrick Kypson", "Emil Ruusuvuori", "Terence Atmane", "Daniil Medvedev",
           "Alexander Zverev", "Dominik Koepfer", "Kwon Soon-Woo", "Lukas Klein", "James McCabe", "Alex Michelsen",
           "Bernabe Zapata Miralles", "Jiri Lehecka", "Cameron Norrie", "Juan Pablo Varillas Patino-Samudio",
           "Dusan Lajovic", "Giulio Zeppieri", "Max Purcell", "Mate Valkusz", "Albert Ramos Vinolas", "Casper Ruud",
           "Tommy Paul", "Gregoire Barrere", "Marcos Giron", "Jack Draper", "Miomir Kecmanovic", "Yosuke Watanuki",
           "Rinky Hijikata", "Jan-Lennard Struff", "Alexander Bublik", "Sumit Nagal", "Mackenzie McDonald",
           "Shang Juncheng", "Daniel Evans", "Lorenzo Sonego", "Richard Gasquet", "Carlos Alcaraz")

playing_hand = c("R", "R", "R", "R", "R", "R", "R", "R", "L", "R", "R", "R", "R", "R", "R",
                 "L", "R", "R", "R", "L", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R",
                 "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R",
                 "L", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R", "R",
                 "R", "R", "R", "R", "R", "R", "R", "L", "R", "R", "R", "L", "R", "R", "L",
                 "R", "R", "R", "L", "R", "L", "R", "R", "R", "R", "R", "L", "R", "R", "R",
                 "R", "R", "R", "R", "R", "R", "L", "R", "R", "L", "R", "R", "R", "R", "R",
                 "R", "L", "R", "R", "L", "R", "R", "L", "R", "R", "R", "R", "L", "R", "R",
                 "R", "R", "R", "R", "R", "L", "R", "R", "R", "R")
backhand = c("TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "OH", "TH", "TH", "OH", "TH", "TH",
             "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "OH", "TH", "TH", "TH", "TH",
             "TH", "TH", "OH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "OH", "OH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "TH", "OH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "TH", "TH", "OH", "TH", "TH", "TH", "OH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "TH", "TH", "OH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH", "TH",
             "TH", "TH", "TH", "TH", "TH", "TH", "OH", "TH", "OH", "TH")

record2023 = c(8.9, 3.8, 5.0, 5.0, 5.1, 5.8, 4.8, 5.3, 6.4, 5.4, 4.8, 4.4, 4.5, 5.4, 4.5, 5.1, 7.0, 3.3, 4.4, 3.6,
               5.8, 5.0, 3.3, 5.9, 5.3, 4.7, 2.9, 3.9, 3.9, 4.5, 2.5, 6.7, 8.1, 4.8, 0.0, 4.1, 2.9, 4.6, 5.1, 5.4,
               6.5, 5.4, 5.0, 3.3, 3.8, 2.5, 3.8, 6.5, 6.4, 5.6, 5.7, 0.0, 5.3, 3.7, 4.2, 6.7, 6.2, 0.0, 4.6, 3.7,
               5.1, 4.3, 4.0, 6.9, 6.5, 4.9, 5.8, 0.0, 5.8, 4.3, 5.1, 6.0, 5.9, 4.2, 5.3, 3.5, 5.0, 7.5, 0.0, 6.6,
               6.6, 5.1, 4.8, 5.0, 6.0, 3.3, 2.4, 5.4, 5.4, 4.4, 3.9, 3.3, 0.0, 5.1, 2.5, 7.9, 6.7, 5.4, 4.4, 0.0,
               0.0, 4.7, 4.2, 5.7, 5.9, 4.6, 5.1, 2.5, 3.3, 5.0, 3.2, 6.1, 6.0, 4.7, 4.5, 6.1, 4.7, 4.2, 5.0, 5.4,
               4.6, 6.0, 5.4, 3.3, 4.1, 5.0, 3.7, 8.4)


serve_rating = c(8.9, 7.0, 8.5, 7.3, 7.8, 8.1, 8.0, 8.1, 8.0, 8.3, 7.5, 6.9, 8.0, 7.9, 8.0, 8.4, 8.7, 7.6, 7.5, 6.8, 7.9,
                 8.3, 6.9, 7.6, 7.9, 8.0, 7.4, 7.3, 8.1, 8.4, 7.8, 8.9, 8.7, 7.6, 5.0, 7.7, 7.5, 7.8, 8.1, 7.7, 8.6, 8.0,
                 8.1, 7.1, 7.6, 7.4, 7.9, 8.4, 7.9, 8.7, 8.1, 0.0, 8.0, 8.3, 7.6, 8.8, 8.4, 0.0, 8.8, 8.6, 8.6, 7.3, 8.1,
                 8.4, 8.3, 7.4, 8.2, 7.7, 8.2, 7.9, 8.2, 8.6, 8.2, 7.3, 8.0, 6.7, 8.0, 8.3, 0.0, 8.8, 8.4, 7.9, 7.3, 
                 8.7, 8.5, 7.5, 6.6, 7.8, 8.4, 8.2, 7.1, 6.8, 4.1, 7.9, 7.8, 8.5, 8.4, 7.7, 8.0, 7.9, 0.0, 8.1, 6.8, 8.1, 8.1,
                 7.4, 7.6, 7.7, 7.9, 8.4, 7.5, 8.3, 8.1, 8.1, 8.1, 8.6, 7.9, 8.2, 7.3, 8.3, 8.2, 8.7, 7.9, 7.6, 7.8, 8.2,
                 7.5, 8.5)

return_rating = c(2.9, 2.2, 1.5, 2.5, 2.2, 2.3, 1.9, 2.1, 2.6, 1.9, 2.1, 2.6, 1.7, 2.2, 2.0, 1.6, 2.3, 2.0, 2.2, 2.0, 2.5,
                  1.4, 1.6, 2.8, 2.5, 1.9, 1.6, 1.9, 1.5, 1.6, 1.4, 1.9, 2.9, 2.2, 1.1, 2.1, 1.8, 1.9, 2.1, 2.6, 2.1, 1.8,
                  2.1, 1.6, 1.6, 1.3, 1.9, 2.4, 2.8, 1.3, 1.9, 0.0, 1.9, 1.6, 2.4, 1.8, 2.1, 0.0, 1.5, 1.0, 1.2, 2.1, 1.8,
                  2.5, 2.2, 2.1, 2.0, 0.5, 1.9, 1.4, 2.2, 1.6, 2.2, 2.7, 1.9, 2.6, 2.1, 1.8, 0.0, 1.6, 2.4, 2.2, 2.2,
                  1.6, 1.5, 1.4, 2.3, 2.6, 1.7, 1.6, 1.9, 1.4, 2.9, 2.1, 1.8, 3.1, 2.3, 2.0, 1.7, 1.1, 0.0, 1.9, 2.7, 1.9, 2.5,
                  2.2, 2.2, 2.0, 1.8, 1.5, 2.2, 2.3, 2.4, 1.9, 2.1, 2.6, 2.2, 1.5, 2.5, 1.9, 1.6, 0.7, 2.5, 2.0, 2.1, 1.8,
                  1.9, 3.1)


hcrating = c(9.3, 2.5, 4.4, 5.0, 2.5, 6.1, 5.6, 4.1, 6.5, 5.1, 5.0, 1.3, 3.7, 5.0, 4.6, 6.0, 7.5, 3.3, 2.5, 5.0,
             5.8, 5.0, 3.3, 5.2, 4.0, 5.4, 2.0, 3.3, 4.1, 4.0, 1.3, 6.5, 8.4, 5.3, 0.0, 1.0, 2.1, 5.0, 5.1, 4.6,
             6.2, 5.4, 4.6, 6.0, 5.0, 3.3, 1.9, 6.5, 6.7, 6.0, 5.8, 0.0, 5.0, 3.2, 4.0, 6.3, 6.7, 0.0, 4.1, 3.6,
             4.2, 4.5, 2.5, 6.2, 5.4, 4.8, 5.7, 0.0, 5.8, 5.0, 4.6, 6.1, 6.7, 4.6, 5.0, 0.0, 4.6, 5.0, 0.0, 6.9,
             6.5, 5.0, 5.0, 5.0, 5.6, 3.8, 2.9, 5.7, 5.8, 3.2, 3.0, 0.0, 0.0, 5.6, 2.5, 8.0, 6.3, 5.8, 4.4, 0.0,
             0.0, 3.3, 2.1, 5.5, 4.8, 3.3, 4.8, 0.0, 3.6, 5.0, 0.8, 4.8, 6.5, 4.2, 4.8, 6.4, 4.9, 4.2, 4.4, 3.8,
             3.6, 6.0, 6.0, 3.6, 4.3, 5.0, 4.5, 7.6)


win_vs_left = c(10.0, NA, 0.0, 0.0, 6.0, 6.7, 5.0, 6.7, 8.3, 5.7, 2.0, 8.3, 7.5, 10.0, NA, 0.0, 7.8, 0.0, 6.0, 0.0, 5.0, NA, NA, 8.8, 7.1, 5.0, 0.0,
                4.0, 10.0, 2.5, 10.0, 5.0, 8.3, 6.0, NA, 7.1, 3.3, 7.1, 3.3, 3.3, 9.1, 6.0, 0.0, 0.0, 5.0, 5.0, 6.0, 8.6, 8.2, NA, 6.7, NA, 0.0, 2.9, 10.0,
                6.3, 6.0, NA, 5.0, 4.0, 7.5, 1.7, 5.0, 8.3, 5.7, 7.5, 7.8, 0.0, 4.0, NA, 5.0, 10.0, 6.7, 3.3, 7.5, 6.0, 6.7, NA, NA, 7.1, 10.0, 5.7, 0.0,
                3.3, 3.3, 6.0, 1.7, 10.0, 6.7, 5.6, 0.0, NA, NA, 10.0, 0.0, 7.5, 9.2, NA, 6.6, NA, NA, 3.3, 2.5, 7.5, 8.0, 5.6, 3.3, NA, 0.0, NA, 0.0,
                6.7, 5.7, 5.0, 4.4, 3.3, 6.0, 5.7, 6.0, 3.3, 7.5, NA, 5.0, 5.0, 5.0, 6.7, 2.9, 8.8)

win_vs_right = c(8.8, 3.8, 5.6, 10.0, 5.0, 5.7, 4.5, 5.0, 5.9, 5.3, 5.4, 3.5, 4.1, 4.9, 4.5, 5.4, 6.9, 4.0, 4.3, 4.0, 6.0, 5.0, 3.3, 5.5, 5.0, 4.7, 3.3, 
                 3.6, 3.5, 5.0, 1.8, 6.9, 8.1, 4.7, 0.0, 3.2, 2.6, 3.8, 5.5, 5.7, 5.9, 5.1, 5.3, 4.3, 3.3, 1.3, 3.4, 6.2, 6.1, 5.6, 5.6, NA, 5.9, 3.9, 3.6,
                 6.7, 6.2, NA, 4.5, 3.6, 4.0, 4.5, 3.8, 6.7, 6.6, 4.6, 5.5, 0.0, 6.0, 4.3, 5.2, 5.7, 5.8, 4.3, 5.0, 2.7, 4.8, 7.5, NA, 6.6, 6.4, 4.9, 5.7,
                 5.4, 6.9, 2.7, 2.6, 5.0, 5.3, 3.9, 4.3, 3.3, 0.0, 4.4, 3.3, 7.9, 6.3, 4.6, 3.8, 0.0, NA, 5.0, 4.1, 5.5, 5.7, 4.2, 5.5, 2.5, 3.8, 5.0, 3.6,
                 6.0, 6.1, 4.7, 4.6, 6.4, 4.5, 3.3, 4.7, 5.7, 4.3, 6.0, 5.5, 2.5, 4.0, 4.6, 3.9, 8.4)


win_vs_ohbh = c(7.8, 0.0, 8.0, NA, 6.7, 10.0, 0.0, 3.3, 6.7, 5.7, 2.5, 3.3, 3.3, 6.7, 3.3, 2.5, 8.8, NA, 2.9, 0.0, 10.0, NA, NA, 2.5, 2.0, 2.5, 5.0, 10.0,
                6.0, 8.6, 0.0, 7.0, 7.9, 2.0, NA, 3.3, 5.0, 6.7, 2.5, 5.0, 6.4, 4.3, 5.0, NA, NA, 10.0, 2.5, 1.7, 3.3, 0.0, 0.0, NA, 10.0, 2.5, 0.0, 6.0,
                10.0, NA, 6.7, 3.3, 5.0, 3.3, 10.0, 6.7, 8.0, 3.3, 4.3, NA, 6.7, 0.0, 8.0, 3.3, 7.1, 3.3, 8.3, 5.0, 5.0, 10.0, NA, 8.0, 7.8, 5.0, 6.0, 6.7,
                10.0, 5.0, 0.0, 0.0, 0.0, 5.0, 6.7, 0.0, NA, 1.4, NA, 9.2, 8.3, 10.0, 0.0, 0.0, NA, 0.0, 2.5, 8.0, 0.0, 3.3, 5.0, 0.0, 6.0, 10.0, 3.3, 10.0,
                10.0, 0.0, 8.0, 10.0, 4.0, NA, 0.0, 8.0, 4.3, 10.0, 5.0, NA, 6.7, 5.7, 5.0, 9.3)

win_vs_thbh = c(9.1, 4.3, 4.6, 5.0, 5.2, 5.2, 4.2, 5.0, 6.0, 5.0, 5.2, 4.6, 4.7, 5.6, 4.5, 5.6, 6.8, 3.3, 4.8, 3.0, 3.8, 5.0, 3.3, 6.2, 5.5, 5.0, 2.0, 2.2,
                3.3, 4.2, 3.0, 6.7, 8.2, 5.1, 0.0, 4.2, 2.7, 4.4, 5.2, 5.6, 6.0, 5.0, 5.0, 3.3, 3.8, 1.8, 3.9, 7.2, 6.7, 6.3, 6.5, NA, 4.5, 4.2, 5.0, 6.8,
                6.0, NA, 4.3, 3.8, 5.0, 3.9, 3.3, 6.9, 6.2, 5.0, 6.0, 0.0, 5.6, 6.0, 4.7, 6.3, 5.7, 4.1, 4.7, 3.1, 4.5, 6.7, NA, 6.4, 6.4, 4.9, 4.4, 4.6,
                5.0, 3.2, 3.0, 5.5, 5.6, 4.1, 1.5, 3.3, 0.0, 5.6, 2.5, 7.6, 6.4, 4.3, 5.0, 0.0, NA, 5.0, 4.3, 5.5, 6.6, 3.6, 5.1, 3.3, 3.3, 0.0, 2.9, 6.0,
                5.9, 5.9, 4.2, 5.9, 4.9, 4.2, 5.8, 5.0, 4.7, 5.0, 5.5, 3.3, 3.7, 4.6, 3.4, 8.3)

gs_record2023 = c(9.6, NA, 3.3, NA, 2.0, 6.7, 5.7, 6.4, 5.0, 5.6, 2.5, 2.5, 4.3, 0.0, 5.7, 7.1, 6.7, 0.0, 4.3, 3.3, 3.3, NA, NA, 6.4, 5.6, 5.7, 0.0, 2.0, 2.5,
              2.0, 0.0, 7.8, 7.5, 4.3, NA, 2.0, 4.3, 4.3, 5.0, 3.3, 7.1, 3.3, 0.0, 0.0, NA, 0.0, 4.3, 7.5, 6.7, 3.3, 5.7, NA, 0.0, 4.3, 0.0, 6.7, 5.6, NA,
              3.3, 3.3, 5.0, 3.3, 6.7, 7.8, 7.1, 6.0, 5.6, 0.0, 2.5, 5.0, 6.3, 4.3, 4.3, 5.0, 5.0, 0.0, 7.0, 6.7, NA, 6.9, 7.1, 6.0, 6.0, 5.0, 6.7, 2.0, 2.0,
              6.4, 4.3, 2.0, 2.5, 0.0, 0.0, 4.0, NA, 7.7, 7.5, 0.0, 0.0, NA, NA, 5.0, 2.0, 6.7, 6.4, 5.0, 0.0, 5.0, 2.0, NA, 0.0, 6.9, 7.3, 2.0, 4.3, 5.0, 0.0,
              4.0, 6.7, 0.0, 4.3, NA, 4.3, 0.0, 5.0, 5.6, 0.0, 9.0)

elo = c(2226.7, 1606.9, 1738.7, 1532.8, 1738.3, 1874.8, 1855.0, 1765.5, 1852.9, 1807.0, 1769.1, 1625.4, 1719.0, 1755.0, 1796.4, 1892.4, 1946.6, 1701.1, 1685.8,
         1675.6, 1739.5, 1772.1, 1392.2, 1864.7, 1791.6, 1723.8, 1634.9, 1683.8, 1702.4, 1791.0, 1667.5, 1973.9, 2196.7, 1813.2, 1592.2, 1638.8, 1636.8, 1734.1,
         1780.1, 1814.3, 1863.5, 1832.4, 1831.7, 1530.4, 1648.5, 1644.0, 1691.0, 1870.5, 1945.1, NA, 1851.0, 1498.8, 1729.1, 1691.3, 1631.5, 1875.9, 1871.3, 1591.0,
         1707.3, 1682.8, 1757.3, 1693.9, 1698.5, 2020.5, 1936.0, 1819.7, 1820.4, 1613.2, 1819.2, 1616.3, 1857.7, 1870.5, 1930.4, 1717.6, 1752.1, 1628.9, 1827.8,
         1653.3, 1339.1, 1983.1, 2010.9, 1802.2, 1774.2, 1773.3, 1725.5, 1711.3, 1693.3, 1856.2, 1898.1, 1769.2, 1655.8, 1511.4, 1612.6, 1809.2, 1633.6, 2104.4,
         2024.0, 1701.7, 1725.8, 1658.3, 1447.1, 1632.6, 1688.9, 1799.8, 1814.6, 1667.6, 1748.7, 1611.1, 1679.6, 1549.2, 1667.5, 1895.1, 1879.8, 1716.4, 1788.1,
         1876.2, 1749.2, 1732.4, 1654.0, 1823.4, 1804.2, 1573.4, 1799.6, 1609.3, 1782.6, 1786.4, 1691.8, 2148.8)

AO_data <- data.frame(Player = player, Playing_Hand = playing_hand, Backhand = backhand, Record2023 = record2023,
                      HC_Rating = hcrating, GS_Record2023 = gs_record2023, Serve_Rating = serve_rating,
                      Return_Rating = return_rating, Win_vs_Left = win_vs_left, Win_vs_Right = win_vs_right,
                      Win_vs_OHBH = win_vs_ohbh, Win_vs_THBH = win_vs_thbh, ELO = elo)

rownames(AO_data) <- NULL
AO_data[is.na(AO_data)] <- 0.0
AO_data

attach(AO_data)

library(knitr)


### Functions for prediction ###

prediction <- function(a, b) {
  # Playing Hand
  win_a_hand <- if (b$Playing_Hand == "R") a$Win_vs_Right else a$Win_vs_Left
  win_b_hand <- if (a$Playing_Hand == "R") b$Win_vs_Right else b$Win_vs_Left
  
  # Backhand
  win_a_bh <- if (b$Backhand == "TH") a$Win_vs_THBH else a$Win_vs_OHBH
  win_b_bh <- if (a$Backhand == "TH") b$Win_vs_THBH else b$Win_vs_OHBH
  
  # coefficients
  elo_diff       <- a$ELO - b$ELO
  win_pct_diff   <- (a$Record2023 - b$Record2023) * 100
  serve_diff     <- (a$Serve_Rating - b$Serve_Rating) * 100
  return_diff    <- (a$Return_Rating - b$Return_Rating) * 100
  hc_diff        <- (a$HC_Rating - b$HC_Rating) * 100
  gs_diff      <- (a$GS_Record2023 - b$GS_Record2023) * 100
  matchup_hand      <- (win_a_hand - win_b_hand) * 100
  matchup_bh        <- (win_a_bh - win_b_bh) * 100
  
  # weighted coefficients
  coeff <- (
    0.30 * elo_diff +
      0.10 * win_pct_diff +
      0.10 * serve_diff +
      0.20 * return_diff +
      0.10 * hc_diff +
      0.10 * gs_diff +
      0.10 * matchup_hand +
      0.10 * matchup_bh
  )
  
  # set-result 
  if (coeff > 200) {
    return("3:0")
  } else if (coeff > 100) {
    return("3:1")
  } else if (coeff > 0) {
    return("3:2")
  } else if (coeff > -100) {
    return("2:3")
  } else if (coeff > -200) {
    return("1:3")
  } else {
    return("0:3")
  }
}





round_df <- function(data) {
  df <- data.frame(Player1 = character(),
                   Player2 = character(),
                   pred_result = character(),
                   stringsAsFactors = FALSE)
  
  for (i in seq(1, nrow(data) - 1, by = 2)) {
    Player1 <- data[i, ]
    Player2 <- data[i + 1, ]
    
    pred_result <- prediction(Player1, Player2)
    
    df <- rbind(df, data.frame(
      Player1 = Player1$Player,
      Player2 = Player2$Player,
      Prediction = pred_result,
      stringsAsFactors = FALSE
    ))
  }
  
  return(df)
}


model_eval <- function(df) {
  correct_winner <- 0
  correct_result <- 0
  
  for (i in 1:nrow(df)) {
    prediction <- df$Prediction[i]
    result <- df$Result[i]
    
    # Set results
    p_a <- as.numeric(substr(prediction, 1, 1))
    p_b <- as.numeric(substr(prediction, 3, 3))
    
    r_a <- as.numeric(substr(result, 1, 1))
    r_b <- as.numeric(substr(result, 3, 3))
    
    if ((p_a > p_b && r_a > r_b) || (p_a < p_b && r_a < r_b)) {
      correct_winner <- correct_winner + 1
    }
    
    if (p_a == r_a && p_b == r_b) {
      correct_result <- correct_result + 1
    }
  }
  
  pct_winner <- round(correct_winner / nrow(df) * 100, 1)
  pct_result <- round(correct_result / nrow(df) * 100, 1)
  
  cat("Correct winners:", correct_winner, "of", nrow(df),
      paste0("(", pct_winner , "%)\n"))
  cat("Correct results:", correct_result, "of", nrow(df),
      paste0("(", pct_result , "%)\n"))
  
  invisible(list(correct_winner = correct_winner,
                 correct_result = correct_result))
}


#### First Round ####


R1_Results <- c("3:1", "3:0", "0:3", "0:3", "3:2", "0:3", "3:2", "0:3", "3:2", "1:3", "3:1", "2:3", "3:1", "2:3", "2:3", "1:3", "3:0", "3:1", "3:2", "1:3",
                "3:1", "3:0", "2:3", "1:3", "3:0", "3:0", "3:2", "3:2", "3:2", "3:1", "3:0", "2:3", "3:1", "2:3", "3:1", "2:3", "3:1", "3:0", "0:3", "0:3",
                "3:1", "2:3", "0:3", "0:3", "3:2", "2:3", "1:3", "1:3", "3:1", "1:3", "1:3", "0:3", "3:0", "1:3", "3:1", "0:3", "3:0", "2:3", "3:1", "2:3",
                "0:3", "2:3", "1:3", "0:3")



round1_df <- round_df(AO_data)
round1_df$Result <- R1_Results


round1_df %>%
  kbl(caption = "Australian Open 2024 - First Round Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")


model_eval(round1_df)

#### Second Round ####



round_winners <- function(df, col_name = "Result") {
  winner <- c()
  
  for (i in 1:nrow(df)) {
    set <- df[[col_name]][i]
    scores <- as.numeric(unlist(strsplit(set, ":")))
    
    if (length(scores) != 2 || any(is.na(scores))) {
      winner <- c(winner, NA)
    } else if (scores[1] == 3) {
      winner <- c(winner, df$Player1[i])
    } else if (scores[2] == 3) {
      winner <- c(winner, df$Player2[i])
    } else {
      winner <- c(winner, NA)
    }
  }
  
  return(winner)
}

R1_winners <- round_winners(round1_df)
R1_winners


R2_players <- AO_data[AO_data$Player %in% R1_winners, ]
R2_players

round2_df <- round_df(R2_players)


R2_Results <- c("3:1", "0:3", "3:2", "1:3", "3:0", "3:0", "2:3", "1:3", "3:0", "1:3", "0:3", "1:3", "3:0", "1:3", "3:0", "0:3",
                "1:3", "1:3", "3:1", "2:3", "3:1", "3:0", "3:1", "2:3", "3:2", "3:1", "3:2", "2:3", "3:1", "3:2", "1:3", "1:3")

round2_df$Result <- R2_Results


round2_df %>%
  kbl(caption = "Australian Open 2024 - Second Round Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")


model_eval(round2_df)



#### Third Round ####

R2_winners <- round_winners(round2_df)
R2_winners


R3_players <- AO_data[AO_data$Player %in% R2_winners, ]
R3_players

round3_df <- round_df(R3_players)
round3_df

R3_Results <- c("3:0", "3:2", "3:1", "0:3", "3:0", "1:3", "3:0", "0:3",
                "3:0", "1:3", "1:3", "0:3", "3:0", "3:1", "2:3", "0:3")

round3_df$Result <- R3_Results


round3_df %>%
  kbl(caption = "Australian Open 2024 - Third Round Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")


model_eval(round3_df)


#### Fourth Round ####

R3_winners <- round_winners(round3_df)
R3_winners


R4_players <- AO_data[AO_data$Player %in% R3_winners, ]
R4_players

round4_df <- round_df(R4_players)
round4_df

R4_Results <- c("3:0", "3:2", "3:0", "2:3", "0:3", "1:3", "3:2", "0:3")

round4_df$Result <- R4_Results

round4_df %>%
  kbl(caption = "Australian Open 2024 - Fourth Round Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")


model_eval(round4_df)



#### Quarterfinal ####

R4_winners <- round_winners(round4_df)
R4_winners


QF_players <- AO_data[AO_data$Player %in% R4_winners, ]
QF_players

QF_df <- round_df(QF_players)
QF_df

QF_Results <- c("3:1", "3:0", "2:3", "3:1")

QF_df$Result <- QF_Results

QF_df %>%
  kbl(caption = "Australian Open 2024 - Quarterfinal Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")

model_eval(QF_df)


#### Semifinal ####

QF_winners <- round_winners(QF_df)
QF_winners


SF_players <- AO_data[AO_data$Player %in% QF_winners, ]
SF_players

SF_df <- round_df(SF_players)
SF_df

SF_Results <- c("1:3", "3:2")

SF_df$Result <- SF_Results

SF_df %>%
  kbl(caption = "Australian Open 2024 - Semifinal Results", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")

model_eval(SF_df)


#### Final ####

SF_winners <- round_winners(SF_df)
SF_winners


F_players <- AO_data[AO_data$Player %in% SF_winners, ]
F_players

F_df <- round_df(F_players)
F_df

F_Result <- c("3:2")

F_df$Result <- F_Result

F_df %>%
  kbl(caption = "Australian Open 2024 - Final Result", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")

model_eval(F_df)




#### Tournament ####

tournament_df <- rbind(
  round1_df,
  round2_df,
  round3_df,
  round4_df,
  QF_df,
  SF_df,
  F_df)
tournament_df

tournament_df %>%
  kbl(caption = "Australian Open 2024", align = "c") %>%
  kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
                full_width = F, position = "center")


model_eval(tournament_df)


