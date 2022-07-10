# Depen­dency In­ver­sion Prin­ciple

> **Principe**
>
>*Les classes de haut ni­veau ne de­vraient pas dé­pendre des classes de bas ni­veau. Elles de­vraient dé­pendre toutes les deux d’abs­trac­tions. Une abs­trac­tion ne doit pas dé­pendre des dé­tails. Les dé­tails doi­vent dé­pendre de l’abs­trac­tion.*

Gé­né­ra­le­ment, lorsque vous con­ce­vez un lo­gi­ciel, vous pou­vez faire la dis­tinc­tion entre deux ni­veaux de classes.

* Les **classes de bas ni­veau** im­plé­men­tent des trai­te­ments ba­siques comme uti­li­ser le disque, trans­fé­rer des don­nées sur un ré­seau, se con­nec­ter à une base de don­nées, etc.

* Les **classes de haut ni­veau** con­tien­nent la lo­gique mé­tier qui in­dique aux classes de bas ni­veau ce qu’elles doi­vent faire.

Naturellement, nous avons tendance à concevoir les classes de bas niveau afin de les exploiter dans celles de haut niveau. 
Cela est courant lorsque l'on dé­ve­lop­pe le pro­to­type d’une nouvelle application car nous n'avons qu'une vague idée de ce que l'on va pou­voir faire à haut ni­veau, car le code de bas ni­veau n’est pas très clair ou pas en­core im­plé­menté.

Avec une telle ap­proche, les classes de la lo­gique mé­tier ont ten­dance à de­ve­nir dé­pen­dantes des classes pri­mi­tives de bas niveau.

Le prin­cipe d’in­ver­sion des dé­pen­dances pro­pose de chan­ger le sens de cette dépendance.

1. Pour com­men­cer, vous devez **dé­crire les in­ter­faces pour les trai­te­ments** de bas ni­veau dont les classes de haut ni­veau vont avoir be­soin, de pré­fé­rence en uti­li­sant les termes de la lo­gique mé­tier. 

Par exemple, imaginons une application qui doit lire un fichier de rapport. 
La lo­gique mé­tier **doit** ap­pe­ler une mé­thode `ouvrirRapport(fichier)` plu­tôt qu’une suite de mé­thodes `ouvrirFichier(x)`, `lireOctets(n)`, `fermerFichier(x)`. 

**Ces in­ter­faces font par­tie du haut niveau.**

2. Main­te­nant, vous pou­vez rendre les classes de haut ni­veau dé­pen­dantes de ces in­ter­faces, plu­tôt que de les rendre dé­pen­dantes des classes con­crètes de bas ni­veau. Cette dé­pen­dance sera bien plus faible que celle d’ori­gine.

3. Une fois que les classes de bas ni­veau im­plé­men­tent ces in­ter­faces, elles de­vien­nent dé­pen­dantes de la lo­gique mé­tier, in­ver­sant la di­rec­tion de la dé­pen­dance originale.

Le prin­cipe d’in­ver­sion des dé­pen­dances est sou­vent uti­lisé en cor­ré­la­tion avec le prin­cipe **Open/Closed** : vous pou­vez étendre les classes de bas ni­veau pour uti­li­ser dif­fé­rentes classes de la lo­gique mé­tier sans avoir à mo­di­fier les classes existantes.