![](OGD-Leitfaden-V1.07fr-1_1.jpg)  
![](OGD-Leitfaden-V1.07fr-1_2.jpg)  
   
   
   
   
   
   
   
**Guide **  
   
   
**Open Government Data pour géodonnées **  
   
   
   
   
   
   

* * *

   
  
   
   
   
   
**Mentions légales **  
   
**Titre **  
Open Government Data (OGD), guide pour les géodonnées   
   
**Version **  
1.07-fr du 22 juin 2017   
   
**Donneur d’ordre **  
Conférence suisse sur l’informatique – Groupe de travail sur les systèmes d’information géographique   
(CSI-SIG)   
   
**Auteurs **  
•  Manfred Loidold   
•  Thomas Strösslin   
   
**Nous remercions les personnes suivantes pour leur contribution lors des entretiens: **  
•  Pasquale di Donato (Office fédéral de topographie)   
•  Cyrill Durrer (Oyatec AG)   
•  Christine Egli (canton AG)   
•  Kuno Epper (canton SZ)   
•  André Golliez (opendata.ch)   
•  Priska Haller (canton ZH)   
•  Meinrad Huser (Huser Bau- und Immobilienrecht)   
•  Patrick Ibele (Office fédéral de topographie)   
•  Christian Kaul (canton ZH)   
•  René L’Eplattenier (canton SG)   
•  Christian Laux (opendata.ch)   
•  Juan Pablo Lovato (Archives fédérales)   
•  Matthias Mazenauer (canton ZH)   
•  Daniel Peter (canton LU)   
•  Mario Schaffhauser (canton LU)   
•  André Schneider (Office fédéral de topographie)   
•  Marco Sieber (ville de Zurich)   
•  Peter Staub (canton GL)   
•  Fridolin Wicki (Office fédéral de topographie)   
•  Anne Wiedmer (Archives fédérales)   
... ainsi que CadastreSuisse pour les résultats du sondage des cantons sur la situation des OGD en   
avril 2017.   
   
   
   
_**Pour des raisons de lisibilité, seule la forme masculine a été utilisée ici. Il va de soi que les deux genres **_  
_**sont concernés. **_  
   
   
   
   

* * *

   
  
   
   
   
   
**Sommaire**   
[**1.** **Introduction et but ..................................................................................................... 6** ](OGD-Leitfaden-V1.07frs.html#7)  
[1.1  Situation de départ ....................................................................................................................... 6   
1.2  Objectifs et public cible ................................................................................................................. 6   
](OGD-Leitfaden-V1.07frs.html#7)[1.3  Contenu et structure ..................................................................................................................... 7   
1.4  Gestion du cycle de vie du document ........................................................................................... 7 ](OGD-Leitfaden-V1.07frs.html#8)  
[**2.** **Notions relatives à l’Open Data................................................................................... 8** ](OGD-Leitfaden-V1.07frs.html#9)  
[2.1  Open Data ..................................................................................................................................... 8   
2.2  Open Government Data (OGD) ..................................................................................................... 8   
](OGD-Leitfaden-V1.07frs.html#9)[2.3  Linked Open Data .......................................................................................................................... 9   
2.4  Conséquences et résumé .............................................................................................................. 9 ](OGD-Leitfaden-V1.07frs.html#10)  
[**3.** **Notions relatives au droit de la géoinformation (LGéo, OGéo) .................................... 10** ](OGD-Leitfaden-V1.07frs.html#11)  
[**4.** **Concordance entre les OGD et le droit de la géoinformation, applicabilité des OGD pour **](OGD-Leitfaden-V1.07frs.html#13)  
[**les géodonnées .......................................................................................................... 12**   
](OGD-Leitfaden-V1.07frs.html#13)[4.1  Conditions légales ....................................................................................................................... 14   
](OGD-Leitfaden-V1.07frs.html#15)[4.2  Conditions techniques ................................................................................................................ 18   
](OGD-Leitfaden-V1.07frs.html#19)[4.3  Big data et conséquences ........................................................................................................... 19 ](OGD-Leitfaden-V1.07frs.html#20)  
[**5.** **Opportunités et risques des OGD ............................................................................... 20** ](OGD-Leitfaden-V1.07frs.html#21)  
[5.1  Opportunités et possibilités ........................................................................................................ 20   
](OGD-Leitfaden-V1.07frs.html#21)[5.2  Risques ........................................................................................................................................ 21 ](OGD-Leitfaden-V1.07frs.html#22)  
[**6.** **Le lancement pratique des OGD ................................................................................. 22** ](OGD-Leitfaden-V1.07frs.html#23)  
[6.1  Choix des géodonnées pour les OGD .......................................................................................... 25   
](OGD-Leitfaden-V1.07frs.html#26)[6.2  Traitement de «données plus anciennes», mise à jour et états temporels ............................... 26   
6.3  Système d’étoiles pour le label de qualité OGD ......................................................................... 26   
6.4  Tâches à réaliser pour l’introduction des OGD ........................................................................... 26   
](OGD-Leitfaden-V1.07frs.html#27)[6.5  A-t-on besoin d’une loi sur les OGD? .......................................................................................... 27   
6.6  Qu’en est-il de la certification? ................................................................................................... 27   
](OGD-Leitfaden-V1.07frs.html#28)[6.7  Valeurs empiriques/meil eures pratiques ................................................................................... 28 ](OGD-Leitfaden-V1.07frs.html#29)  
[**7.** **Vue d’ensemble des portails OGD .............................................................................. 30** ](OGD-Leitfaden-V1.07frs.html#31)  
[**8.** **Aperçu de l’utilisation des LOD .................................................................................. 30** ](OGD-Leitfaden-V1.07frs.html#31)  
[**9.** **Bibliographie, liens utiles ........................................................................................... 31** ](OGD-Leitfaden-V1.07frs.html#32)  
   
   

* * *

   
3    
   
   
**Management Summary **  
   
Les données des institutions publiques sont de plus en plus souvent rendues accessibles sous la forme d’Open Go-  
vernment Data (OGD). En Suisse également, le Conseil fédéral a élaboré une stratégie OGD et le portail OGD open-  
data.swiss est lui aussi opérationnel. Le présent guide entend répondre aux objectifs suivants: montrer aux res-  
ponsables des géodonnées des autorités fédérales, indépendamment de leur niveau, le cheminement d’une publi-  
cation sur opendata.swiss et décrire tant les décisions nécessaires que leurs conséquences.   
   
Dans l’idéal, les données ouvertes (Open Data) impliquent une publication pour une utilisation, une modification   
et une transmission libres, et ce pour tout usage. Cela suppose des exigences obligatoires (lisibilité par des ma-  
chines p. ex.) et la possibilité de définir des restrictions (indication obligatoire de la source p. ex.). Les OGD sont   
el es aussi soumises à des conditions d’utilisation correspondantes («licences» basées sur le droit privé). La publi-  
cation en tant que Linked Open Data (LOD) pose des exigences techniques plus strictes et contribue à la produc-  
tion et à l’échange automatique de connaissances (Semantic Web).    
   
Le droit de la géoinformation poursuit les mêmes buts que l’OGD, avec cependant des différences dans les détails   
et la réalisation. Les buts de l’OGD ne peuvent donc pas être totalement atteints, entre autres en raison des dispo-  
sitions concernant les émoluments et des restrictions en cas d’une utilisation commerciale.   
   
En mai 2017, les points suivants étaient en vigueur pour la publication des géodonnées sur opendata.swiss:   
•  La publication de géodonnées de base gratuite au niveau d’autorisation d’accès «A» peut-être couverte de   
manière très satisfaisante.   
•  Il est également possible de publier des géodonnées gratuites   
o  Dont l’utilisation non commerciale est autorisée sans condition et   
o  Dont l’utilisation commerciale est régie par certaines conditions.   
•  La publication de données dont l’utilisation non commerciale est également encadrée par certaines condi-  
tions est incompatible avec les Open Data et n’est pas possible sur opendata.swiss.   
•  Les géodonnées payantes ne peuvent pas être publiées sur opendata.swiss.   
   
Concernant les conditions d’utilisation, le site opendata.swiss permet de déterminer si:   
•  L’indication de la source est facultative ou obligatoire,   
•  L’autorisation du fournisseur de données est nécessaire en vue d’une utilisation commerciale.   
   
En outre, dans le cadre de la publication des OGD, le contrôle des points suivants est nécessaire:   
•  Qualité des données: la clause de non-responsabilité n’est pas défendable juridiquement car la responsa-  
bilité souveraine ne peut pas être exclue.   
•  Protection des données: en raison des nouvel es méthodes de big data, il est plus facile d’établir l’identité   
des personnes, sans déployer d’efforts excessifs.   
•  Les violations du droit d’auteur sont certes très rares, mais pas exclues.   
   
Les opportunités liées aux OGD sont visibles au niveau politique (participation, instauration de la confiance, etc.),   
organisationnel (efficacité de la gestion) et économique (potentiel de marché). Les risques sont patents en cas de   
publication peu rigoureuse ou d’une utilisation inappropriée des données, ainsi qu’en cas de dépendance à un   
changement de paradigme au niveau politique ou administratif, qui semble encore incertain sur le long terme.    
   
La question de la nécessité d’une loi relative aux OGD est controversée. En théorie, les objectifs OGD pourraient   
être atteints à l’aide de lois spécifiques, mais les experts interrogés sont plutôt d’avis que ce serait trop peu le cas   
en pratique.   
   
**Le guide opérationnel des publications sur opendata.swiss se trouve au chap. 6. **  
  
  
   

* * *

   
4    
   
**Glossaire[1 ](OGD-Leitfaden-V1.07frs.html#5)**  
   
CF   
Conseil fédéral   
Cst.   
Constitution fédérale de la Confédération suisse; RS 101   
csv   
Comma Separated Value (format de données)   
docx   
Format de données pour fichier texte de Microsoft Word   
LPD   
Loi fédérale sur la protection des données; RS 235.1   
dxf   
Drawing Interchange File Format   
dwg   
(de «Drawing») format de données propriétaire, binaire   
PFPDT   
Préposé fédéral à la protection des données et à la transparence   
eCH   
Standards E-Government   
ecw   
Enhanced Compression Wavelet (format de trame de données)   
FLAC   
Free Lossless Audio Codec (format de données audio)   
LGéo   
Loi fédérale sur la géoinformation: RS 510.62   
OGéo   
Ordonnance sur la géoinformation; RS 510.620   
GeoJSON   
Géo-dialecte du format texte JSON (voir ce mot)   
GeoPackage   
Standard ouvert, non propriétaire pour les géodonnées   
GeoTIFF   
Fichier TIFF géoréférencé (format de trame de données)   
gml   
Geography Markup Language (langage de balisage XML pour les géodonnées)   
gpx   
GPS Exchange Format (format de données XML pour les géodonnées)   
INTERLIS   
Langage de description pour géodonnées (standard)   
http   
Hypertext Transfer Protocol (protocole de transmission de données sur un réseau informa-  
tique)   
JPEG2000   
Format d’image du Joint Photographic Experts Group   
JSON   
JavaScript Object Notation (format de données textuel es)   
KML   
Keyhole Markup Language (langage de balisage XML pour les géodonnées)   
LOD   
Linked Open Data   
MGDM   
Modèle minimal de géodonnées   
MPEG   
Format de données vidéo du Moving Picture Experts Group   
OData   
Open Data Protocol   
ods   
Open Document Spreadsheet (format tableur)   
odt   
Open Document Text (format de données texte)     
ogg   
Format de données conteneur pour données multimédia   
png   
Portable Network Graphics (format de données graphiques)   
RDF   
Resource Description Framework (modèle de représentation des connaissances dans le   
Web)   
LOGA   
Loi sur l’organisation du gouvernement et de l’administration; RS 172.010   
   
1 Sources: Wikipédia, giswiki.hsr.ch et filedesc.com (consulté la dernière fois le 03.05.17)   
   

* * *

   
5    
   
Shape file   
Format de géodonnées d’ESRI   
SPARQL   
Langage de requête agissant sur des données RDF   
RS   
Recueil systématique du droit fédéral   
svg   
Scalable Vector Graphics (spéc. basée XML pour la description de vecteurs)   
tiff   
Tagged Image File Format (format de trame de données)   
URI   
Unique Ressource Identifier pour l’adressage univoque de ressources sur Internet   
LRCF   
Loi fédérale sur la responsabilité de la Confédération, des membres de ses autorités et de   
ses fonctionnaires (Loi sur la responsabilité); RS 170.32   
vorbis   
Format de données conteneur pour données multimédia   
wave   
Format de données audio de Microsoft et IBM   
WebM   
Format conteneur pour données audio et vidéo   
wld   
ArcGIS World Data   
WMS   
Web Map Service (géoservice pour la visualisation de cartes)   
WMTS   
Web Map Tile Service (géoservice pour la visualisation performante de cartes avec tuiles)   
WFS   
Web Feature Service (géoservice pour l’accès à des données vectorielles sur le Web)   
xlsx   
Format de données Microsoft Excel pour tableur   
xml   
Extensible Markup Language (langage de balisage extensible sous forme de texte)   
   
   
   

* * *

   
6    
   
**1. Introduction et but **  
**1.1 **  
**Situation de départ **  
Que ce soit en Suisse ou au niveau international, les données sont rendues accessibles de manière croissante sous   
la forme d’«Open Data». En 2014, le Conseil fédéral a certes déterminé la stratégie Open Government Data (OGD)   
Suisse, mais il n’existe pas de loi OGD. Depuis début 2016, les Archives fédérales exploitent le portail OGD national   
opendata.swiss.   
   
OGD ne signifie pas ici un processus purement technique, mais:   
•  Suppose une compréhension modifiée par la sphère politique: une plus grande transparence et participa-  
tion des citoyens, la renonciation aux recettes issues de la vente de données, etc.;   
•  Exige de la disponibilité, de l’ouverture d’esprit et des adaptations dans les administrations.   
   
La progression des OGD est inégale en Suisse - et dépend principalement de la politique. On trouve des arguments   
en faveur des OGD dans divers domaines:   
•  **Processus politique:** p. ex. plus grande transparence des décisions politiques, plus de confiance des ci-  
toyens, participation plus forte de ces derniers et un gain d’image en général;   
•  **Effets organisationnels**: p. ex. une administration efficace, qui collabore mieux avec d’autres institutions   
et avec l’économie;   
•  **Aspects économiques**: p. ex. création de valeur à partir de nouvelles prestations, ou meil eure proximité   
avec les clients des services publiant leurs informations.   
**1.2 **  
**Objectifs et public cible **  
Le guide s’adresse aux autorités qui souhaitent ou doivent publier des géodonnées en tant que Open Government   
Data. Il a vocation à leur indiquer la marche à suivre pour la publication et les conséquences des décisions qu’elles   
devront prendre. Dans ce contexte, opendata.swiss joue le rôle de plateforme de publication primaire.   
   
De plus, le guide doit:   
•  Permettre la compréhension commune des notions utilisées;   
•  Signaler les conflits entre le cas Open Data idéal, la stratégie OGD de la Confédération/opendata.swiss   
ainsi que le traitement des géodonnées en théorie et dans la pratique;   
•  Apporter une aide concrète lors de la préparation de géodonnées en tant qu’OGD. Des indications sont   
données pour les étapes suivantes en particulier:   
o  Les critères définissant quel es données peuvent être préparées en tant qu’OGD,   
o  La tarification et les conditions d’utilisation compatibles avec les OGD,   
o  Les particularités en vigueur (responsabilité, mise à jour, etc.).   
•  Renvoyer aux portails suisses courants.   
   
Le but de l’exercice n’est pas:   
•  D’élaborer des solutions de résolution des conflits entre le cas Open Data idéal, la stratégie OGD de la   
Confédération/opendata.swiss et le droit de la géoinformation,   
•  De décrire plus précisément les Linked Open Data,   
•  De définir les géodonnées devant être publiées en tant qu’OGD.   
   

* * *

   
7    
   
**1.3 **  
**Contenu et structure **  
Les chapitres[ 2 et](OGD-Leitfaden-V1.07frs.html#9) 3 contiennent les informations de base importantes, nécessaires à la bonne compréhension de   
l’ensemble du document. Les chapitres 4 et[ 5 ](OGD-Leitfaden-V1.07frs.html#21)présentent les directives de publication de géodonnées sous la   
forme d’OGD et les arguments pour et contre. Le processus de publication, détaillé dans le chapitre 6, représente   
le noyau de ce document. Les autres chapitres complètent et précisent des thèmes choisis.   
   
Dans le détail, la conception est la suivante:   
•  Le c[hap. 2 d](OGD-Leitfaden-V1.07frs.html#9)éfinit les notions importantes et montre les interdépendances.   
•  Le chap. 3 propose les définitions de notions du droit de la géoinformation importantes pour les OGD.   
•  Le chap. 4 décrit les différences entre le cas Open Data idéal, la stratégie OGD de la Confédération/open-  
data.swiss et le droit de la géoinformation ainsi que les conditions légales et techniques.   
•  Le c[hap. 5 p](OGD-Leitfaden-V1.07frs.html#21)asse en revue les opportunités et les risques impliqués par les OGD.   
•  Le chap. 6 décrit les aspects pratiques de la publication des OGD et commence par un graphique du pro-  
cessus de publication de géodonnées sur opendata.swiss.   
•  Le c[hap. 7 d](OGD-Leitfaden-V1.07frs.html#31)onne un aperçu général des principaux portails OGD.   
•  Le c[hap. 8 m](OGD-Leitfaden-V1.07frs.html#31)ontre des exemples de LOD.   
•  Le chap. 9 répertorie la bibliographie.    
   
**Les éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss** figurent dans ce   
genre d’encadrés.   
   
**1.4 **  
**Gestion du cycle de vie du document **  
Lors de la rédaction, on a constaté qu’il restait encore des questions en suspens et des travaux encore à terminer.   
Ce guide doit donc rester «vivant» et être régulièrement passé en revue pour vérifier que les contenus sont encore   
actuels. Cela peut concerner, d’une part, la mise en œuvre opérationnelle (implémentation d’opendata.swiss, in-  
novations techniques.. ) et, d’autre part, les modifications des prescriptions de la sphère politique et de l’adminis-  
tration ou encore en raison de la jurisprudence.   
   
   
   

* * *

   
8    
   
**2. Notions relatives à l’Open Data **  
**2.1 **  
**Open Data **  
Le terme Open Data[2](OGD-Leitfaden-V1.07frs.html#9) (données en libre accès) **désigne des données accessibles à tous sans restrictions, libres **  
**d’utilisation, de diffusion et de réutilisation**. Les Open Data nécessitent les éléments suivants:   
•  Une licence ouverte (définie dans le tableau 2, colonne «Open Data, cas idéal»;   
•  L’accès à des données complètes, à des coûts de reproduction uniques et mesurés;   
•  Un format ouvert sous une forme utilisable et modifiable (pas d’obstacles techniques inutiles en particu-  
lier) et la lisibilité par machine.    
   
Il existe pour les licences ouvertes:   
•  Des exigences obligatoires (p. ex. utilisation pour chaque usage) ainsi que   
•  Des dispositions facultatives pouvant être formulées par le fournisseur de données, qui sont dès lors con-  
traignantes (p. ex. indication de la source, changement de nom en cas de modification).   
D’autres informations se trouvent sur (opendefinition.org, 2017) et au chap. 4, dans le tableau comparant la stra-  
tégie OGD de la Confédération/opendata.swiss avec le droit de la géoinformation.   
**2.2 **  
**Open Government Data (OGD) **  
Les **OGD** sont «**tous les volumes de données du secteur public, rendus accessibles par l’État et l’administration **  
**dans l’intérêt général, en vue de leur utilisation, diffusion et réutilisation libres**[»2.](OGD-Leitfaden-V1.07frs.html#9)   
   
Selon plusieurs sources[3](OGD-Leitfaden-V1.07frs.html#9), dix principes s’appliquent aux OGD:   
1.  Intégralité: données primaires, métadonnées et éventuel ement formules de calcul   
2.  Données primaires pour la vérification, ainsi que le type de saisie des données   
3.  Proximité temporel e; idéalement en temps réel   
4.  Accès facilité aux données; cela comprend l’accessibilité pour les personnes à mobilité réduite (absence   
d’entraves) et l’utilisation de plusieurs langues.   
5.  Lisibilité par des machines   
6.  Absence de discrimination: chacun doit pouvoir accéder en tout temps aux données, sans devoir fournir   
son identité ou d’autres justifications.   
7.  Utilisation de standards ouverts afin d’assurer l’indépendance à l’égard des fabricants.   
8.  Concession de licence[4:](OGD-Leitfaden-V1.07frs.html#9) les données publiques doivent être à disposition librement et de manière géné-  
rale, sans restrictions d’utilisation.    
9.  Assurer la disponibilité à long terme des données. Les mises à jour ou des modifications doivent pouvoir   
être compréhensibles.    
10.  Coûts d’utilisation: également une utilisation commerciale doit être gratuite.    
   
Selon la stratégie OGD de la Confédération[5](OGD-Leitfaden-V1.07frs.html#9), les données des administrations sont considérées comme librement   
accessibles en présence des conditions suivantes: leur accès est libre et leur utilisation n’est pas limitée pour des   
raisons relevant du droit de la protection des données ou de l’information ou du droit d’auteur, ce qui permet à   
des tiers de les réutiliser librement.   
   
2 (Von Lucke & Geiger, 2010) Cité dans Wikipédia (dernière consultation le 05.05.2017); vaut pour tout le paragraphe.   
3 (Sunlight Foundation, 2014) (Geiger & Von Lucke, 2012) (Paderta, 2012) (Seuß, 2015) (Tauberer, 2017)   
4 La notion de «concession de licence» provenant des sources s’oppose au droit suisse en particulier.   
5 (Schweizerischer Bundesrat, 2014, S.3494)[: https://www.admin.ch/opc/de/federal-gazette/2014/3493.pdf   
](https://www.admin.ch/opc/de/federal-gazette/2014/3493.pdf)   

* * *

   
9    
   
**2.3 **  
**Linked Open Data **  
Les Linked Open Data (LOD) désignent: **«des données librement disponibles sur le World Wide Web, qui sont **  
**identifiées par un URI (Uniform Resource Identifier**) et qui peuvent grâce à celui-ci être **consultées directement **  
**via le protocole HTTP et qui renvoient à d’autres données également à l’aide d’un URI.**» Idéalement, on emploie   
le Resource Description Framework (RDF) et des standards qui l’utilisent (SPARQL et Web Ontology Language   
(OWL)) pour le codage et la mise en lien des données, si bien que les Linked Open Data sont simultanément une   
partie du Web sémantique.»[6 ](OGD-Leitfaden-V1.07frs.html#10)  
   
Les composants de base sont des triplets RDF, qui représentent les données comme sujet, prédicat et objet et per-  
mettent ainsi une mise en réseau de type graphe. Les LOD associent des données ou des parties de données et   
génèrent ainsi un nouveau savoir. Les LOD sont axées exclusivement sur le traitement par machines et exigent une   
grande exactitude technique (voir chap[. 4.2.1, 4.2.2,](OGD-Leitfaden-V1.07frs.html#19)[ 4.3,](OGD-Leitfaden-V1.07frs.html#20)[ 6.7)](OGD-Leitfaden-V1.07frs.html#29). Le c[hap. 8 ](OGD-Leitfaden-V1.07frs.html#31)propose des exemples de RDF et de por-  
tails/points de terminaison (Endpoints) LOD.   
**2.4 **  
**Conséquences et résumé **  
Les principes de l’Open Data forment la base des OGD et peuvent être pris plus ou moins en considération. Dans le   
cas le plus simple, il peut s’agir de n’importe quel jeu de données mis publiquement à disposition par une autorité,   
p. ex. l’organigramme d’un office. Mais c’est seulement à travers la formulation d’exigences (p. ex. utilisation com-  
merciale, indication de la source) que les dispositions nécessaires sont prises et qu’au final, l’utilité des données   
est garantie.   
   
Par rapport au cas idéal des Open Data, la stratégie OGD de la Confédération met en évidence:   
a)  Des correspondances:   
•  On vise la gratuité, mais des exceptions ne sont pas exclues (p. ex. coûts marginaux, donc factura-  
tion du travail requis pour la mise à disposition des données)   
•  Lisibilité par machines et formats ouverts   
•  Principe de l’absence de discrimination   
•  Mention de qualité d’auteur   
b)  Des différences dans l’ouverture des licences, là où le Conseil fédéral/opendata.swiss permettent des res-  
trictions (p. ex. condition d’utilisations «ASK?» sur opendata.swiss pour une utilisation commerciale; voir   
c[hap. 4.1.1)](OGD-Leitfaden-V1.07frs.html#15), ce qui ne correspond pas à l’Open Data.   
c)  La définition de l’Open Data exige (ce qui n’est pas mis en œuvre dans la stratégie OGD de la Confédéra-  
tion/opendata.swiss):   
•  Le marquage des modifications peut être exigé.   
•  Les données doivent pouvoir être utilisables en tout ou partie.   
•  Il est admissible d’interdire des restrictions techniques pour la transmission des données; p. ex.   
pas de diffusion dans un format propriétaire.   
   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  Les cas idéaux de l’Open Data ne sont pas totalement réalisés dans la stratégie OGD de la Con-  
fédération/opendata.swiss.   
•  Les attentes et objectifs dans le domaine de l’Open Data exigent dans la réalité des compro-  
mis, des concessions et des restrictions, mais ils doivent rester présents à l’esprit.   
   
  
   
6 Selon Wikipédia, consulté la dernière fois le 05.05.2017.   
   

* * *

   
10    
   
**3. Notions relatives au droit de la géoinformation (LGéo, OGéo) **  
La liste des notions issues du droit de la géoinformation se limite à la législation suisse (tab. 1)[7.](OGD-Leitfaden-V1.07frs.html#11)   
  **Terme **  
**Définition/explication  **  
**Source**[8](OGD-Leitfaden-V1.07frs.html#11)  
Géodonnées   
Données à référence spatiale qui décrivent l’étendue et les proprié-  
Art. 3,   
tés d’espaces et d’objets donnés à un instant donné, en particulier   
let. a   
la position, la nature, l’utilisation et le statut juridique de ces élé-  
ments.   
Géodonnées de   
Géodonnées reposant sur un acte législatif fédéral, cantonal ou   
Art. 3,   
base   
communal.   
let. c   
Géométadonnées  Descriptions formel es des caractéristiques de géodonnées   
Art. 3,   
let. g   
Service compétent  Le législation désigne les services responsables de la saisie, la mise à   
**o  **Art. 8,   
jour et la gestion des géodonnées de base.   
al. 1   
Accès aux géodon- Les géodonnées de base relevant du droit fédéral sont accessibles à   
**LGé **Art. 10   
nées   
la population et peuvent être utilisées par chacun à moins que des   
intérêts publics ou privés prépondérants ne s’y opposent.   
Dispositions et     
Le service chargé de la saisie, de la mise à jour et de la gestion des   
Art. 12,   
restrictions d’utili- géodonnées de base peut subordonner l’accès aux géodonnées de   
al. 1   
sation   
base relevant du droit fédéral ainsi que leur utilisation et leur trans-  
mission à une autorisation.   
Émoluments (ta-  
La Confédération et les cantons peuvent percevoir des émoluments   
Art. 15,   
rif)   
pour l’accès aux géodonnées de base et pour leur utilisation.   
al. 1   
Service de télé-  
Service Internet permettant de télécharger des copies de jeux de   
Art. 2,   
chargement[9 ](OGD-Leitfaden-V1.07frs.html#11)  
géodonnées ou des parties de ces jeux et, lorsque c’est possible, d’y   
let. j   
accéder directement.   
Niveaux d’autori-  
•  Niveau A: géodonnées accessibles au public   
Art. 21   
sation d’accès   
•  Niveau B: géodonnées partiellement accessibles au public   
pour les géodon-  
•  Niveau C: géodonnées non accessibles au public   
nées de base   
Accès aux géodon- Dans des cas particuliers ou pour certaines parties du jeu de don-  
Art. 22   
nées de base de   
nées dans le cas général, l’accès est limité, différé ou refusé, s’il:   
al. 2   
niveau A   
a)  Entrave  l’exécution de mesures concrètes prises par une   
autorité conformément à ses objectifs;   
b)  Risque de compromettre la sûreté intérieure ou extérieure   
**éo **  
de la Suisse;   
c)  Risque  de compromettre les intérêts de la Suisse ou d’un   
**OG**  
canton en matière de politique extérieure et ses relations in-  
ternationales;   
d)  Risque de compromettre les relations entre la Confédération   
et les cantons ou les relations entre cantons;   
e)  Risque de compromettre les intérêts de la politique écono-  
mique ou monétaire de la Suisse;   
f)  Peut révéler des secrets professionnels, d’affaires    
g)  Ou de fabrication;   
h)  Risque d’enfreindre l’obligation de garder le secret fixé dans   
une loi spéciale.    
   
   
7 La directive INSPIRE de l’UE n’est pas prise en compte, car elle ne vaut en prinicipe pas pour la Suisse.   
8 En dehors de la LGéo et de l’OGéo, l’OGéo-swisstopo (RS 510.620.1) et l’ordonnance sur les émoluments (RS 510.620.2)   
peuvent également être intéressantes concernant des informations complémentiares.    
9 On renonce ici à donner les définitions d’autres géoservices (représentation, ...) car ceux-ci sont moins pertinentes pour   
les OGD.   
   

* * *

   
11    
   
**Terme **  
**Définition/explication  **  
**Source**[8](OGD-Leitfaden-V1.07frs.html#11)  
Accès aux géodon- Aucun accès n’est garanti aux géodonnées de base de niveau B.   
Art. 23   
nées de base de   
   
niveau B   
Dans des cas particuliers ou, dans le cas général, pour la totalité du   
jeu de données ou certaines de ses parties, l’accès est accordé si:   
•  Aucun intérêt lié au maintien du secret ne s’y oppose ou   
•  les intérêts liés au maintien du secret peuvent être sauve-  
gardés par des mesures juridiques, organisationnel es ou   
techniques.   
Autorisation d’uti- L’autorisation d’utilisation à des fins commerciales est délivrée si:   
Art. 25,   
lisation   
•  L’accès aux géodonnées peut être accordé;   
al. 2   
•  L’intéressé est enregistré;   
   
•  L’intéressé a déclaré le but, l’intensité et la durée de l’utili-  
   
sation;   
   
•  L’émolument est fixé par une décision ou un contrat ou   
   
qu’il a été préalablement perçu;   
   
•  Les données de niveau B peuvent également être rendues   
   
accessibles aux tiers auxquels il est prévu des les trans-  
   
mettre.   
   
L’autorisation peut être limitée dans le temps si l’utilisation de don-  
   
nées ayant perdu de leur actualité fait courir des risques.   
al. 3   
   
   
Le but, l’intensité ou la durée d’utilisation peuvent être limités si le   
   
montant de l’émolument dépend de ces facteurs.   
**éo  **al. 4   
Protection des   
Les utilisateurs sont responsables du respect des dispositions rela-  
Art. 29   
données   
tives à la protection des données.   
**OG**  
   
Ils sont tenus d’informer sans délai le service visé à l’art. 8, al. 1   
LGéo, ainsi que le préposé fédéral à la protection des données et à   
la transparence, des mesures prises afin de respecter ces disposi-  
tions.   
Indication de la   
Les géodonnées de base ne peuvent être reproduites qu’avec l’indi-  
Art. 30   
source   
cation de la source.   
Utilisation par des  Les obligations auxquel es les utilisateurs sont soumis valent égale-  
Art. 31   
tiers   
ment pour les tiers auxquels des géodonnées de base sont trans-  
mises.   
Protection des   
Le service destinataire est responsable du respect des dispositions   
Art. 39   
données, maintien  relatives à la protection des données et au maintien du secret.   
du secret   
   
Le service diffuseur informe le service destinataire de l’existence de   
prescriptions particulières.   
Transmission à   
Une autorité peut donner l’accès à des tiers aux géodonnées de base   
Art. 40   
des tiers   
et permettre leur utilisation si:   
•  Elle applique les mêmes prescriptions en matière d’accès et   
d’utilisation que le service visé à l’art. 8, al. 1, LGéo;   
•  Elle indique l’actualité des géodonnées;   
•  Elle perçoit les émoluments prévus et les reverse au service   
visé à l’art. 8, al. 1, LGéo.   
Tab. 1: Notions importantes du droit de la géoinformation relatives aux OGD   
   
  
   

* * *

   
12    
   
**4. Concordance entre les OGD et le droit de la géoinformation, appli-**  
**cabilité des OGD pour les géodonnées **  
Fondamentalement, les OGD, la stratégie OGD de la Confédération/opendata.swiss et le droit de la géoinforma-  
tion poursuivent les mêmes objectifs: rendre accessibles au public des données sous une forme utilisable, afin de   
soutenir des activités économiques et rendre accessible à la population un précieux savoir. Il existe cependant des   
différences quant à la réalisation et au niveau de détail.   
Le tableau suivant met cela en évidence. Dans la colonne Droit de la géoinformation, les conflits sont marqués en   
rouge:   
•  _Italique: _conflits avec le cas idéal de l’Open Data (réalisation complète des objectifs de l’Open Data)   
•  Souligné: conflits avec la stratégie OGD de la Confédération/opendata.swiss   
  **N°**[10](OGD-Leitfaden-V1.07frs.html#13)_**Cas idéal Open Data **_  
**Stratégie OGD de la Confédération  **  
**Droit de la géoinformation **  
**opendata.swiss **  
1.1   
Une licence ouverte est obli-  
OGD en tant que précepte d’action   
Des géodonnées accessibles   
gatoire. Les cel ules suivantes  («open by default»). Des restrictions  et utilisables, si relevant du   
portant un numéro 2.x de   
sont possibles; une utilisation libre   
droit privé, pour autant   
cette colonne définissent les   
reste privilégiée. La notion de licence  qu’el es ne s’opposent pas à   
éléments caractérisant une li-  
n’est pas admissible pour le secteur   
des intérêts publics ou privés.   
cences ouverte (open licence).  étatique, car relevant du droit privé   
_Il existe des restriction[s11 12 15.](OGD-Leitfaden-V1.07frs.html#13)_   
(d’où des «conditions d’utilisation»).   
1.2    
En principe gratuites; certains  En principe exemption d’émolu-  
La Confédération et les can-  
2.1.1  coûts sont admis, lorsque leur  ment ; les coûts sont à maintenir à   
tons peuvent percevoir _des _  
2.1.9  montant ne constitue pas une  un niveau minimum. Opendata.swiss  _émoluments pour l’accès aux _  
restriction d’accès de facto.   
n’encourage pas la publication de   
_géodonnées de base et pour _  
données payantes.   
_leur utilisation._[11](OGD-Leitfaden-V1.07frs.html#13)   
1.3   
Lisibilité par machines obliga-  
Lisibilité par machines obligatoire.   
Lisibilité par machines obliga-  
1.4   
toire. Formats appropriés et   
Les formats ouverts sont un objectif.  toire. _Des formats non ou-_  
ouverts modifiables.   
Des formats non ouverts sont égale-  
_verts sont également publiés._   
ment publiés sur opendata.swiss.   
2.1.2  La licence doit permettre la   
La stratégie OGD de la Confédération  Diffusion, également pour   
diffusion, y compris la vente   
ne mentionne pas de «vente» ou uti- une utilisation commerciale;   
(«sale»).   
lisation «commerciale». Pour cette   
_ici, une restriction est admis-_  
dernière, une restriction est possible  _sibl[e12.](OGD-Leitfaden-V1.07frs.html#13)_   
sur opendata.swiss .[12](OGD-Leitfaden-V1.07frs.html#13)   
2.1.3  La licence doit permettre la   
Pas exigé   
Pas exigé   
modification des données.   
2.1.4  La licence doit permettre l’uti- Pas exigé   
«Parties» spécifiées p. ex.   
lisation de la totalité ainsi que   
pour des services de téléchar-  
de parties de données.   
gement[13 ](OGD-Leitfaden-V1.07frs.html#13)et autorisation   
d’accès[14 ](OGD-Leitfaden-V1.07frs.html#13)  
2.1.5  La licence doit permettre une  Pas exigé   
Pas exigé   
compilation avec d’autres   
œuvres.   
2.1.6  Pas de discrimination de per-  
Est implicite, puisque l’accès aux   
_Autorisation d’accès[15](OGD-Leitfaden-V1.07frs.html#13)_Exis-  
2.1.7  sonnes/de groupes, les droits  données sur opendata.swiss est pos-  
tence d’un transfert des obli-  
s’appliquent à tous.   
sible sans enregistrement.   
gations sur l’utilisateur.[16](OGD-Leitfaden-V1.07frs.html#13)  
   
10 selon (opendefinition.org, 2017)   
11 LGéo, art. 15 al. 1:   
12 La condition d’utilisation «ASK?» exige l’autorisation du fournisseur de données pour une utilisation commerciale (voir sou[s 2.4) ](OGD-Leitfaden-V1.07frs.html#10)   
13 OGéo, art. 2, let. j,   
14 OGéo, art. 22, al. 2   
15 Des restrictions p. ex. au niveau «B» ne sont pas forcément compréhensibles et ne s’inscrivent pas dans l’esprit des OGD.   
16 P. ex. pour la protection des données (OGéo, art. 29)   
   

* * *

   
13    
   
**N°**[10](OGD-Leitfaden-V1.07frs.html#13)  
_**Cas idéal Open Data **_  
**Stratégie OGD de la Confédération  **  
**Droit de la géoinformation **  
**opendata.swiss **  
2.1.8  La licence doit permettre une  opendata.swiss: des restrictions pour  Géodonnées de base: large   
utilisation pour chaque usage.  une utilisation commerciale sont   
utilisation, également expli-  
possibles (condition d’utilisation   
cite dans le domaine écono-  
«ASK?»).   
mique[17](OGD-Leitfaden-V1.07frs.html#14); _des restrictions exis-_  
_ten[t12.](OGD-Leitfaden-V1.07frs.html#13)_   
2.2.1  L’exigence d’attributions, de   
opendata.swiss: condition d’utilisa-  
Les indications de la source   
2.2.4  mention de droits d’auteur et  tion «BY»   
sont obligatoires pour les   
d’identification de licence est   
géodonnées de base[18](OGD-Leitfaden-V1.07frs.html#14). Des   
possible.   
droits d’auteur sont attribués   
pour les cartes nationales et   
sont donc admis[19.](OGD-Leitfaden-V1.07frs.html#14)   
2.2.3  L’obligation de distribution   
opendata.swiss: non représentable   
L’art. 31 OGéo correspond à   
dans les mêmes conditions est   
une distribution dans les   
admise.   
mêmes conditions[20](OGD-Leitfaden-V1.07frs.html#14).    
2.2.2  L’obligation de mention de la   
opendata.swiss: non représentable   
Pas explicitement régle-  
2.2.5  source en cas de modification   
menté[21. ](OGD-Leitfaden-V1.07frs.html#14)   
est admise.   
2.2.6  Il est possible d’interdire des   
opendata.swiss: non représentable   
Pas explicitement régle-  
   
limitations techniques dans   
menté.   
l’utilisation des droits de li-  
cence.   
Tab. 2: Comparaison entre les Open Data, la stratégie OGD de la Confédération/opendata.swiss et le droit de la géoin-  
formation   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  Sur opendata.swiss, la publication de géodonnées de base gratuite au niveau d’autorisation d’ac-  
cès «A» peut-être couverte de manière très satisfaisante.   
•  Il est également possible de publier des géodonnées gratuites   
o  Dont l’utilisation non commerciale est autorisée sans condition ET   
o  Dont l’utilisation commerciale est sujette à condition.   
•  La condition d’utilisation «ASK?» a une portée étendue, car elle annule les droits et obligations   
selon les principes OGD en cas d’utilisation commerciale.   
•  La publication de géodonnées, qui associe à d’autres conditions également l’utilisation non com-  
merciale, est incompatible avec les OGD et impossible sur opendata.swiss.   
•  La publication de géodonnées payantes est impossible sur opendata.swiss.   
•  Du point de vue du droit des géodonnées, on observe des conflits avec la stratégie OGD de la Con-  
fédération au niveau des coûts/émoluments ainsi que pour le point de l’«utilisation illimitée».   
•  Il y a de plus des conflits du point de vue du droit des géodonnées avec le cas idéal Open Data en   
raison des niveaux d’autorisations d’accès (p. ex. «B»), des restrictions dans le cadre d’une utilisa-  
tion commerciale et de formats non ouverts utilisés.   
   
   
17 LGéo, art. 1   
18 OGéo, art. 30   
19 LGéo, art. 3, al. 3   
20 (Wiedmer & Seiberth, 2015)   
21 Les art. 30 et 31 OGéo peuvent être interprétés dans le sens d’une indication obligatoire de la source en cas de modification par des tiers.   
   

* * *

   
14    
   
**4.1 **  
**Conditions légales **  
Les conditions légales reposent principalement sur les études réalisées dans le cadre du projet opendata.swiss, qui   
peuvent être consultées sur la page du projet eGovernment Suisse[22.](OGD-Leitfaden-V1.07frs.html#15) La préparation des principaux contenus di-  
rectement sur opendata.swiss aiderait à une meilleure visibilité et à une consultation plus fréquente.    
**4.1.1 **  
**Conditions d’utilisation  **  
Les principaux éléments régissant l’utilisation des OGD sont fixés dans les conditions d’utilisation. Visuel ement,   
elles se rapprochent certes des licences Creative Common. Toutefois, il ne s’agit pas de licences[23](OGD-Leitfaden-V1.07frs.html#15), mais de «tra-  
ductions» des bases légales qui s’appliquent aux données[24.](OGD-Leitfaden-V1.07frs.html#15)   
   
Concernant les conditions d’utilisation actuel ement disponibles sur opendata.swiss[25 ](OGD-Leitfaden-V1.07frs.html#15)(voir chap. 6), il convient de   
tenir compte des points suivants:   
•  Une utilisation non commerciale est toujours permise.   
•  En présence de la condition «BY», la source (auteur, titre et lien vers le jeu de données) doit être indiquée;   
sinon, l’indication de la source est recommandée.   
•  En présence d’une condition «ASK?», une utilisation commerciale doit être soumise à l’autorisation du   
fournisseur des données, ce qui ne correspond pas aux idéaux de l’Open Data.   
Si, lors de publication de géodonnées, des lacunes ou des conflits devaient apparaître entre le droit de la géoinfor-  
mation et ces conditions d’utilisation, il est possible de demander une extension des conditions d’utilisation auprès   
du comité de projet OGD[26.](OGD-Leitfaden-V1.07frs.html#15)   
**4.1.2 **  
**Responsabilité **  
Un avis d’exclusion de responsabilité (disclaimer sur les portails d’OGD) semble régler le problème de la responsa-  
bilité de manière claire. Toutefois, les archives fédérales (Wiedmer & Seiberth, 2015) indiquent que la responsabi-  
lité ne peut être exclue[27](OGD-Leitfaden-V1.07frs.html#15).    
   
Les interviews avec d’autres experts l’ont confirmé. Pour la publication des données, cela signifie:   
•  Malgré la clause de non-responsabilité, une responsabilité peut être engagée selon les circonstances.   
Cette responsabilité est indépendante de la manière dont les données ont été diffusées par l’office.   
•  Les institutions de la Confédération au minimum ne peuvent pas, a priori, voir leur responsabilité exclue[28](OGD-Leitfaden-V1.07frs.html#15).    
•  La question de la responsabilité n’est pas un aspect spécifique des OGD, mais le canton de Zurich, p. ex.,   
peut être tenu responsable de la diffusion de fausses informations, en cas de préméditation ou de négli-  
gence[29](OGD-Leitfaden-V1.07frs.html#15).   
   
Cependant, de l’avis des juristes, la barre de la responsabilité effective est placée très haut:   
•  Il doit y avoir un dommage vérifiable et la causalité doit être prouvée.   
•  Le jeu de données doit avoir été publié spécifiquement pour cet usage - il doit être établit clairement qu’il   
est utilisé dans ce contexte[30.](OGD-Leitfaden-V1.07frs.html#15)   
•  Cela suppose une certaine vitesse au niveau du déroulement.   
   
[22 https://www.egovernment.ch/fr/umsetzung/e-government-schweiz-2008-2015/open-government-data-schweiz/ ](https://www.egovernment.ch/de/umsetzung/e-government-schweiz-2008-2015/open-government-data-schweiz/)  
23 Les licences sont un outil issu du droit privé.   
24 Les bases légales peuvent être publiées sur opendata.swiss, mais ce n’est pas une nécessité.   
25 Les conditions d’utilisation figurent dans le manuel[ (http://handbook.opendata.swiss/fr/prepare/terms.html).](http://handbook.opendata.swiss/de/prepare/terms.html)   
26 Pour les modèles de licence d’opendatacommons.org envisagés comme solution alternative, on remarquera que ceux-ci reposent sur le droit améri-  
cain et leur transposition n’a guère de sens pour la Suisse.   
27 L’art. 3 al. 1 LRCF (Loi sur la responsabilité): «Les art. 3 ss. de la loi fédérale du 14 mars 1958 sur la responsabilité de la Confédération, des membres   
de ses autorités et de ses fonctionnaires (LRCF; RS 170.32) règlent la responsabilité de la Confédération pour les activités officielles réglées par le droit   
public. L’art. 3 al. 1 LRCF prévoit la responsabilité dans les conditions suivantes: dommage, relation avec une activité officielle, causalité adéquate,   
condition de fonctionnaire de l’auteur et illégalité de l’action préjudiciable. Cette responsabilité selon l’art. 3 al. 1 LRCF ne peut être exclue» (Wiedmer   
& Seiberth, 2015), S. 8.   
28 D’autres règles peuvent s’appliquer dans les cantons.   
29 (Laux, 2012), p. 10   
30 Voir aussi (Laux, 2012) p. 9 et p. 12.   
   

* * *

   
15    
   
•  La responsabilité incombe en principe au service capable d’apprécier au mieux le risque et de l’éviter le   
plus facilement.   
•  L’utilisateur des données doit avoir utilisé la meil eure offre; en d’autres termes, s’il utilise des données   
gratuites et non un service payant avec une assurance qualité, il ne peut invoquer une clause de responsa-  
bilité (cheaper cost avoidance).   
Ces énumérations sont sans garantie en ce qui concerne leur intégrité et leur bonne interprétation. En cas de   
doute, il convient d’étudier d’autres publications[31](OGD-Leitfaden-V1.07frs.html#16) et d’entreprendre des contrôles juridiques. S’assurer de la qua-  
lité des données (y compris leur description, le processus de saisie, etc.) par des mesures techniques ou organisa-  
tionnel es est de toute manière recommandé.   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  La clause de non-responsabilité n’est pas défendable juridiquement.   
•  Cependant, la probabilité d’une responsabilité effective est très faible et doit être considérée   
indépendamment des publications OGD.   
•  Une assurance qualité des géodonnées est recommandée dans tous les cas.   
   
**4.1.3 **  
**Protection des données **  
La stratégie OGD de la Confédération[32 ](OGD-Leitfaden-V1.07frs.html#16)exige la prise en compte de la protection des données, oblige les autorités   
à contrôler celles-ci avant publication et nécessite des mesures empêchant l’identification après coup de per-  
sonnes physiques ou morale avec des données agrégées et anonymisées (voir chap.6).   
   
Selon (Wiedmer & Seiberth, 2015) (p. 12-15), des données personnel es selon l’art. 3 let. à LPD sont toutes les indi-  
cations se rapportant à une personne déterminée ou déterminable:   
•  Les «indications» peuvent être de tout genre: informations objectives (p. ex. métier) ou subjectives (p. ex.   
solvabilité). Cela englobe non seulement la vie privée, mais aussi la vie professionnelle ou une activité   
dans une administration. Le genre de saisie et de transmission des données n’est pas pertinent.   
•  Un «lien avec une personne» signifie que les données peuvent être attribuées à une ou plusieurs per-  
sonnes. Cette situation comprend également le cas où il est possible de déduire l’identité d’une personne   
sur la base du contexte ou d’informations complémentaires.   
•  «Identification»/«Traçabilité»: cela comprend l’identification directe et indirecte, p. ex. sur la base d’un   
bien immobilier. Le législateur voit la limite dès le moment où l’identification exige un investissement ex-  
cessif.    
   
La définition de l’investissement «excessif» est en outre sujette à interprétation. Les progrès de la technologie,   
spécialement dans le domaine des big data, exigent un contrôle régulier des dépenses et, le cas échéant, de la ré-  
cupération des données sur le réseau. Les outils et méthodes des big data ont été et sont toujours développés   
pour collecter, lier et analyser les données le plus efficacement possible. La méconnaissance fréquente des algo-  
rithmes d’analyse des données et de leurs répercussions complique en outre l’évaluation juridique.   
   
De plus, on peut se demander si la publication par les autorités et la mise en lien par des entreprises privées ne   
sont pas deux processus séparés, qui doivent être évalués séparément. La publication OGD de données n’exige pas   
la seconde étape, si bien que d’éventuel es violations de la protection des données ne seraient pas imputables aux   
autorités, mais aux entreprises privées.    
   
   
   
   
   
   
   
31 P. ex. (Laux, 2012), (Wiedmer & Seiberth, 2015).   
32 (Schweizerischer Bundesrat, 2014), p. 3501   
   

* * *

   
16    
   
La protection des données doit être vérifiée pour toutes les géodonnées, et également pour les géodonnées de   
base du niveau d’autorisation «A» (voir chap.6). En effet, la classification des données peut être effectuée avant   
l’élaboration des modèles de géodonnées minimaux. Autrement dit, la sensibilité des données a été déterminée   
avant la définition des contenus dans le modèle. Dans tous les cas, il conviendrait donc de vérifier si le contenu   
effectif des données selon le MGDM correspond à l’autorisation d’accès et ne viole pas la protection des données.   
   
**Protection des données: conflit entre le droit fédéral et cantonal? **  
En théorie, un tel conflit ne peut exister, car les lois cantonales relatives à la protection des données ne s’adres-  
sent qu’aux autorités cantonales et communales, alors que la loi sur la protection des données de la Confédération   
s’adresse aux particuliers et aux organes fédéraux[33](OGD-Leitfaden-V1.07frs.html#17).   
   
Des chevauchements ont cependant été constatés dans la pratique:   
•  Là où le canton est l’autorité d’exécution de la Confédération, p. ex. pour la protection de l’environne-  
ment, les mensurations;   
•  Là où les autorités cantonales appliquent le droit fédéral, p. ex. pour la LGéo.   
Pour ces deux points, il semble y avoir des contradictions et ne pas y avoir de consigne claire du côté des cantons   
pour savoir quel droit appliquer. Une discussion plus approfondie dépasserait le cadre du présent guide et n’est   
pas non plus le sujet central de la publication OGD de géodonnées.   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  Les géodonnées peuvent permettre de remonter vers les personnes. La protection des données   
ne peut donc pas être ignorée et el e est ancrée dans le droit de la géoinformation.   
•  Avant la publication de données (qu’il s’agisse d’Open Government Data ou non), il faut dans   
tous les cas s’assurer si la protection des données est respectée.   
•  Malgré le degré d’autorisation d’accès défini dans la loi, il faut vérifier si la protection des don-  
nées pourrait être violée. Il se peut notamment que la cat. A contienne néanmoins des don-  
nées critiques, puisque la répartition des autorisations d’accès peut avoir été effectuée avant   
l’élaboration des MGDM.    
•  Il ne faut pas perdre de vue les progrès des big data et en tenir compte pour toutes les formes   
d’agrégation ou l’anonymisation.   
•  Il ne devrait en principe pas y avoir de chevauchements entre les lois fédérales et cantonales de   
protection des données, mais on en observe dans la pratique.   
   
**4.1.4 **  
**Coûts/fixation des tarifs **  
Dans l’idéal, les OGD sont gratuites, car les émoluments constituent une restriction d’accès. En réalité, il faut ce-  
pendant faire des concessions, p. ex. si le travail pour la mise à disposition des données est très important et qu’il   
en résulte des frais de distribution.   
   
Dans le cadre des entretiens, nous avons pu constater que, pour beaucoup d’offices, une mise à disposition   
payante des données n’est pas rentable si on tient compte de tous les frais, car les frais ne sont pas couverts et on   
peut même observer parfois un déficit (mise à disposition, exploitation d’une boutique ou remise des données,   
encaissement, etc.). Cette observation s’est trouvée confirmée par l’enquête de CadastreSuisse.   
   
De plus, les expériences faites par ViennaGIS montrent que les recettes de la vente de géodonnées chutent, entre   
autres du fait de solutions alternatives gratuites de producteurs commerciaux. Dans le doute, on se rabattrait sur   
les solutions moins chères, avec éventuel ement une moindre qualité, ce qui peut ne pas servir l’intérêt public.   
(Jörg, 2014)   
   
La question de la délimitation par rapport aux prestations individuel es, spécifiques des clients, est d’une impor-  
tance centrale: quand y a-il une tel e délimitation et les données sont-elles payantes? (Bürgi-Schmelz, 2014) cons-  
tate:   
   
33 Art. 2 de la loi sur la protection des données (LPD)   
   

* * *

![](OGD-Leitfaden-V1.07fr-18_1.png)  
   
17    
   
•  Une remise gratuite est à prévoir pour les OGD,   
•  Pour des prestations supplémentaires par contre, une facturation des coûts marginaux doit être prévue.   
La délimitation entre «OGD» et «solutions individuel es, spécifiques des clients» n’est pas bien définie dans tous   
les domaines. La fig. 1 doit permettre d’avoir une meil eure vue d’ensemble.   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
Fig. 1 Question de la pertinence des émoluments selon (Bürgi-Schmelz, 2014), p. 23   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  Le but est la gratuité, mais la réalité (politique) en décide parfois autrement.   
•  Les cantons en particulier doivent déterminer si une remise payante des géodonnées s’avère   
judicieuse, en effectuant un calcul des coûts complets.   
•  La gratuité correspond aux OGD, mais la gratuité n’est pas encore synonyme des OGD - il faut   
pour cela établir d’autres spécifications (p. ex. conditions d’utilisation).   
**4.1.5 **  
**Droit d’auteur **  
Selon (Wiedmer & Seiberth, 2015) p. 9-12, seules les œuvres sont protégées par les droits d’auteur. Les œuvres se   
distinguent par les caractéristiques suivantes:   
•  «Création intellectuelle», donc œuvres humaines uniquement,[34   
](OGD-Leitfaden-V1.07frs.html#18)•  «Littérature et art», qui ne sont cependant pas définis dans la loi. Des œuvres avec un contenu scienti-  
fique tel que des cartes ou des plans peuvent en faire partie.   
•  «Caractère individuel», c.-à-d. se différenciant d’autres œuvres; n’existe pas sous la même forme et ne   
doit pas être créée non plus.[35](OGD-Leitfaden-V1.07frs.html#18)   
   
Le caractère d’une œuvre des contenus d’OGD selon (Wiedmer & Seiberth, 2015) p.10 doit être prouvé pour   
chaque cas: s’agit-il ou non d’œuvres protégées par un droit d’auteur? Il est souvent difficile d’en décider. De ma-  
nière générale, on peut retenir les principes suivants:   
•  Données: les données scientifiques ne sont que rarement protégées par un droit d’auteur, car il leur   
manque en principe le caractère individuel nécessaire;     
•  Les bases et col ections de données peuvent être protégées par un droit d’auteur;   
•  Les textes, images et films peuvent également être protégés par un droit d’auteur.   
   
(Rolf H. Weber, 2000) (p. 32) indique que dans la loi, les cartes sont mentionnées comme une variété d’œuvre à   
contenu scientifique ou technique. Des cartes individualisées, élaborées à l’aide de données, peuvent en faire par-  
tie, même si la base de ces données ne bénéficie pas d’un droit d’auteur. Selon Weber, un droit d’auteur n’est pas   
envisageable pour des données topographiques, des plans cadastraux, des images aériennes et satel ite ou des   
noms géographiques.   
   
   
34 L’ordinateur peut servir d’outil.   
35 Chaque modélisation, généralisation, choix de couleurs et symboles est le choix individuel du créateur. Mais tout cela ne justifie encore pas un droit   
d’auteur.   
   

* * *

   
18    
   
**Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss:   
**Dans la plupart des cas, les questions de droit d’auteur ne sont pas pertinentes pour les géodonnées,   
notamment s’il existe des consignes définies pour la saisie ou la représentation, comme c’est le cas   
pour les géodonnées de base. Le sujet pourrait devenir important dans des cas particuliers, en particu-  
lier pour des données acquises en externe par le biais d’un mandat[36](OGD-Leitfaden-V1.07frs.html#19), pour des photographies ou des   
images créées individuellement (stylisées p. ex.)[37.](OGD-Leitfaden-V1.07frs.html#19) Une éventuel e violation du droit d’auteur doit donc   
être vérifiée dans le cadre de la publication d’OGD, même si ce sera sans résultat dans la plupart des   
cas.    
   
**4.2 **  
**Conditions techniques **  
**4.2.1 **  
**Lisibilité par machine **  
Les données peuvent être traitées sans intervention humaine. Cela exige une source de données stable et bien   
documentée, dont les données sont clairement structurées (Tauberer, 2017) et disponibles dans un format adapté   
(Durrer, 2017).   
   
(Paderta, 2012) P. 23-28 considère les points suivants comme essentiels:   
•  Forme de représentation des ressources de données (format de données, interface);     
•  Description des ressources de données, et la capacité à les trouver (adressage, métadonnées);     
•  Lien sémantique (Linked Data).     
   
La lisibilité par machines n’est pas seulement une question de format, mais aussi de qualité des données.   
Quelques espaces supplémentaires dans le format csv, largement répandu, ne posent pas grand problème pour   
une interprétation des données par les personnes, mais les systèmes cafouil ent et ne génèrent pas de données ou   
alors des données erronées.   
**4.2.2 **  
**Formats et protocoles d’accès **  
Le tableau suivant répertorie les formats importants sur la base des sources consultées[38.](OGD-Leitfaden-V1.07frs.html#19)   
   
**Données structurées**   
CSV, JSON, XML, RDF, XLSX, ODS   
**Documents texte/rapports **  
TXT, XHTML, PDF, DOCX, ODT   
**Formats et protocoles de géodon-**  
GeoJSON, KML, GML, INTERLIS, ESRI shape file, GeoPackage, Geo-  
**nées**   
TIFF, gpx, dxf, dwg, ecw, wld;   
WMS, WMTS, WFS   
**Formats d’image et graphiques**   
TIFF, JPEG2000, PNG, SVG   
**Fichiers audio et vidéo**   
FLAC, WebM, Ogg Vorbis, MPEG4, Wave   
**Divers**   
SPARQL, ODATA (Open Data Protocol);   
Tab. 3: Formats usuels et souvent mentionnés pour les publications OGD[39 ](OGD-Leitfaden-V1.07frs.html#19)  
   
Il convient encore de citer GeoSPARQL en tant que standard de l’Open GeoSpatial Consortium.   
   
   
   
   
   
36 Une communication claire au mandataire et une réglementation contractuelle concernant le droit d’auteur évite des conflits.   
37 (Rolf H. Weber, 2000), p. 30, parle de «sceau de la personnalité de l’auteur».   
[38 http://handbook.opendata.swiss/de/library/empfehlungen-formate#fn:5 (](http://handbook.opendata.swiss/de/library/empfehlungen-formate%23fn:5)Paderta, 2012) («OGD Stadt Zürich: Werkstatt», o. J.) et (Geiger & Von Lu-  
cke, 2012)   
39 Les formats et protocoles indiqués dans le tab. 3 sont conformes aux appellations dans les sources citées, mais ne sont pas des recommandations des   
auteurs.   
   

* * *

   
19    
   
Les exigences générales quant aux formats de données sont les suivantes (Sunlight Foundation, 2014, p. 5):   
•  Réutilisation facile et efficace,   
•  Formats ou standards ouverts,   
•  Au minimum des formats lisibles par machines, mieux structurés.   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
•  Des formats structurés et stables sont recommandés, mais pas des formats propriétaires.   
•  Pour les géodonnées, les formats ou protocoles attendus sont cités.   
   
**4.3 **  
**Big data et conséquences **  
Boostées par les grandes entreprises du secteur de l’informatique (Google, Facebook, . .) et des processus inno-  
vants du traitement de données, les méthodes et technologies issues des big data[40 ](OGD-Leitfaden-V1.07frs.html#20)ont nettement gagné en in-  
fluence et importance. Les big data sont caractérisées par:   
•  High Volume,   
•  High Velocity,   
•  High Variety.   
   
Ce dernier élément gagne en importance pour la question du droit d’auteur, car des images et des films sont de   
plus en plus souvent intégrés.   
   
À part la performance élevée, d’autres particularités des big data sont importantes, d’abord pour la protection des   
données et la désanonymisation des données agrégées:   
•  le «machine learning» rend les systèmes si performants qu’ils s’améliorent sans cesse:   
o  Filtrer les données importantes et spécifiques dans d’immenses quantités de données;   
o  Identifier les erreurs, en tirer des leçons et ainsi les éviter à l’avenir;   
•  Évaluer également des informations non structurées tel es que des textes;   
•  Les technologies des big data ont développé des méthodes spécifiques pour le traitement des géodonnées   
(p. ex. des coordonnées géographiques propres, des algorithmes de recherche très performants) et les   
utilisent pour l’analyse des données (no SQL db Redis, Cassandra, Al egroGraph).   
  **Éléments essentiels relatifs à la publication des géodonnées sur opendata.swiss: **  
Conséquences des big data:   
•  De nouvelles possibilités de mise en lien et de diffusion des données (Semantic Web).   
•  Des LOD sont exigées, afin d’être capable de travailler avec des big data.   
•  Les nouvel es possibilités revêtent une importance critique en ce qui concerne la protection des   
données et, le cas échéant, le droit d’auteur.   
   
  
   
40  Des notions semblables sont la numérisation, la transformation numérique, l’Internet des objets, la 4e révolution industrielle, etc.   
   

* * *

   
20    
   
**5. Opportunités et risques des OGD **  
**5.1 **  
**Opportunités et possibilités **  
Comme dans le chap[. 1.1 ](OGD-Leitfaden-V1.07frs.html#7)concernant l’argumentation et la motivation pour les OGD, le présent document reprend   
la distinction entre les avantages politiques, organisationnels et économiques pour les opportunités[41.](OGD-Leitfaden-V1.07frs.html#21)   
   
**a) Niveau politique[42](OGD-Leitfaden-V1.07frs.html#21)****: **  
•  Preuve de la valeur et de la nécessité des travaux avant tout vis-à-vis de la politique   
•  Prévention du risque que des données de plus mauvaise qualité soient utilisées et distribuées en raison de   
la faible propension à payer les géodonnées[43 ](OGD-Leitfaden-V1.07frs.html#21)  
•  Soutien des milieux de la science, de la recherche et de l’innovation[44   
](OGD-Leitfaden-V1.07frs.html#21)•  Meil eure compréhension des mesures politiques et administratives[45](OGD-Leitfaden-V1.07frs.html#21)   
•  De manière générale, une plus grande transparence renforce la confiance de la population[46](OGD-Leitfaden-V1.07frs.html#21).     
•  Société civile plus forte et plus participative[47](OGD-Leitfaden-V1.07frs.html#21) et atteinte de groupes cibles plus larges[48   
](OGD-Leitfaden-V1.07frs.html#21)•  Plus grande conscience spatiale[49   
](OGD-Leitfaden-V1.07frs.html#21)•  Gain d’image pour la politique[50](OGD-Leitfaden-V1.07frs.html#21); il y a lieu de ne pas passer à côté des développements actuels tels que   
les LOD.    
•  Les conditions d’utilisation amènent clarté et sécurité juridique.   
•  La production et la mise à jour des données sont de toute façon financés par les ressources fiscales[51. ](OGD-Leitfaden-V1.07frs.html#21)   
   
**b) Avantages organisationnels/formels: **  
•  Amélioration de l’efficacité et de la qualité de l’administration[52   
](OGD-Leitfaden-V1.07frs.html#21)•  Meilleure coopération au sein de l’administration et avec d’autres offices[53](OGD-Leitfaden-V1.07frs.html#21)   
•  Contact plus étroit entre le producteur et l’utilisateur de données, simplification de la collaboration[54](OGD-Leitfaden-V1.07frs.html#21)   
•  Détection plus rapide des erreurs du fait d’une utilisation plus large[55   
](OGD-Leitfaden-V1.07frs.html#21)•  En général: vérification et optimisation des processus par une nouvelle forme de publication   
   
**c) Aspects économiques[56](OGD-Leitfaden-V1.07frs.html#21)****: **  
•  Possibilité d’atteindre de nouveaux clients et de soutenir des modèles d’affaires[57](OGD-Leitfaden-V1.07frs.html#21)   
•  Meilleur contact entre l’administration et l’économie par un échange intensif[58](OGD-Leitfaden-V1.07frs.html#21)   
   
41 Voir (Neuroni, Riedl, & Brugger, 2013) p. 1913     
42 (Neuroni, Riedl, & Brugger, 2013, S.1911-1916) On constate qu’en Suisse, l’avantage politique est moins important en raison de la démocratie di-  
recte et de la proximité de la population avec la sphère politique ou l’administration.   
43 (Jörg, 2014)   
44 (Schweizerischer Bundesrat, 2014) (Sunlight Foundation, 2014) (Jörg, 2014) (Paderta, 2012) (Seuß, 2015) (Stadt Zürich, 2012) (Rol i, 2017)   
45 (Schweizerischer Bundesrat, 2014) (Seuß, 2015) (Geiger & Von Lucke, 2012), (Paderta, 2012)   
46 (Paderta, 2012) (Neuroni, Riedl, & Brugger, 2013) (Seuß, 2015) (Rol i, 2017) (Schweizerischer Bundesrat, 2014) et Dietrich cité d’après  (Paderta,   
2012)   
47 (Von Lucke & Geiger, 2010) (Seuß, 2015)  (Open Knowledge International, o. J.)  (Paderta, 2012) (Neuroni, Riedl, & Brugger, 2013) (Stadt Zürich,   
2012)   
48 (Jörg, 2014)  (Seuß, 2015)   
49 (Paderta, 2012)   
50 (Geiger & Von Lucke, 2012)   
51 (Seuß, 2015) et Dietrich cité d’après (Paderta, 2012)   
52 (Schweizerischer Bundesrat, 2014, S.3498) (Seuß, 2015) (Neuroni, Riedl, & Brugger, 2013) (Stadt Zürich, 2012)   
53 (Neuroni, Riedl, & Brugger, 2013) (Seuß, 2015)   
54 (Seuß, 2015)   
55 (Jörg, 2014) (Geiger & Von Lucke, 2012)   
56 (Bürgi-Schmelz, 2013) S.6 estime la création de valeur annuelle issue des OGD à CHF 0,9-1,2 mil iard par an en Suisse.   
57 (Neuroni, Riedl, & Brugger, 2013) (Paderta, 2012) (Rol i, 2017)   
58 (Neuroni, Riedl, & Brugger, 2013) (Jörg, 2014) (Schweizerischer Bundesrat, 2014) et (MCKINSEY GLOBAL INSTITUT 2011) cité d’après (Paderta, 2012)   
   

* * *

   
21    
   
•  De nouvel es prestations et des chaînes de création de valeurs dans des niches peuvent se créer, alors   
qu’elles ne peuvent pas être traitées aujourd’hui faute de ressources des offices[59. ](OGD-Leitfaden-V1.07frs.html#22)   
•  Les géodonnées doivent de toute façon être produites et actualisées pour les besoins des offices.   
**5.2 **  
**Risques **  
En amont:   
•  Implique et nécessite un changement de paradigme dans l’administration.   
•  Il est nécessaire de trouver un langage et des standards communs.   
•  Des personnes insuffisamment qualifiées peuvent interpréter incorrectement les données.   
•  La gratuité peut donner l’impression que les données sont sans valeur.   
•  Dépendant du climat politique général: la tendance va vers les OGD, mais n’est pas stable.   
•  Dangers à cause de la cybercriminalité   
   
Pour la politique et la société:   
•  Perte de recettes avec éventuel ement de petites augmentations des charges[60](OGD-Leitfaden-V1.07frs.html#22)   
•  Distorsion de concurrence: concurrence financée par des rentrées fiscales pour des entreprises qui ont   
éventuellement consenti à de gros investissements pour leurs données (p. ex. prises de vues aériennes)[61.](OGD-Leitfaden-V1.07frs.html#22)   
   
Pour l’administration/le service publiant:   
•  Risques pour la protection de données, risques résiduels pour les questions de responsabilité et de droit   
d’auteur[62 ](OGD-Leitfaden-V1.07frs.html#22)  
•  Erreur dans le choix des données publiées[63](OGD-Leitfaden-V1.07frs.html#22)   
•  Falsification intentionnel e ou par négligences de données par des tiers   
•  Investissement pour la saisie des données (métadonnées: processus de production), la mise à disposition   
des données et l’assurance qualité[64](OGD-Leitfaden-V1.07frs.html#22); celle-ci éventuellement renforcée par la peur de la responsabilité[65 ](OGD-Leitfaden-V1.07frs.html#22)  
•  S’il y a des frais supplémentaires d’un côté et que cette hausse débouche sur un refus politique, la peur   
d’une compression du personnel et d’une diminution des prestations dans l’office peut avoir un effet inhi-  
biteur[66. ](OGD-Leitfaden-V1.07frs.html#22)   
•  Asymétrie: les suppléments de recettes des OGD profitent au fisc, les charges supplémentaires à l’office   
spécialisé[67](OGD-Leitfaden-V1.07frs.html#22).   
•  L’analyse Web et d’utilisateurs automatisée pourrait violer les dispositions de confidentialité et de protec-  
tion des données. Le groupe de travail Droit des OGD et le PFPDT font part de préoccupations concernant   
des solutions utilisées par des serveurs à l’étranger[68;](OGD-Leitfaden-V1.07frs.html#22) état et effets voir contenus OGD de E-Government   
Suisse[69](OGD-Leitfaden-V1.07frs.html#22).    
   
   
59 (Paderta, 2012)   
60 (Bürgi-Schmelz, 2013)   
61 (Seuß, 2015)   
62 (Neuroni, Riedl, & Brugger, 2013) (Seuß, 2015); spécialement par la désagrégation de données anonymisées (Kettiger, 2016)   
63 (Seuß, 2015)   
64 (Seuß, 2015)   
65 (Paderta, 2012)  (Geiger & Von Lucke, 2012)   
66 (Bürgi-Schmelz, 2013)   
67 (Bürgi-Schmelz, 2013)   
68 (Seiberth & Wiedmer, 2015)   
69 https://www.egovernment.ch/fr/umsetzung/e-government-schweiz-2008-2015/open-government-data-schweiz/   
   

* * *

![](OGD-Leitfaden-V1.07fr-23_1.png)  
   
22    
   
**6. Le lancement pratique des OGD **  
Il peut en principe y avoir deux cas d’espèce pour la publication OGD de géodonnées:   
•  Le mandat de publication ou de contrôle de la publication en tant qu’OGD est réalisé en interne, depuis   
l’unité administrative ou le niveau politique supérieur.   
•  Demande externe pour publier des données en tant qu’OGD. Une procédure (Bürgi-Schmelz, 2014), telle   
qu’il ustrée [70](OGD-Leitfaden-V1.07frs.html#23) dans la fig. 2 est recommandée.   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
Fig. 2: Déroulement pour une demande externe selon (Bürgi-Schmelz, 2014), p. 25 (abrégé)   
   
L’illustration suivante (fig.3; «Big Picture») décrit le processus de la publication des géodonnées selon le manuel   
opendata.swiss[71](OGD-Leitfaden-V1.07frs.html#23). La figure doit être actualisée en cas de mise à jour, conformément à la gestion du cycle de vie   
des documents, comme cela est prévu pour 2017[72](OGD-Leitfaden-V1.07frs.html#23).    
   
70 L’enquête de CadastreSuisse confirme que des vœux particuliers (autres formats, pas d’autoréférence) ont un coût.   
71 Voir[ http://handbook.opendata.swiss/fr/publish/swiss.html#publikation-von-geodaten_1;](http://handbook.opendata.swiss/de/publish/swiss.html%23publikation-von-geodaten_1) état au 28.4.2017. Une solution alternative pour publier   
des options non orientées sur des géodonnées consisterait à saisir manuellement des métadonnées via un formulaire web, de les télécharger via un   
fichier XML ou de les télécharger automatiquement via un harvester (moissonneur) [(http://handbook.opendata.swiss/fr/publish/options.html). Le](http://handbook.opendata.swiss/de/publish/options.html))s   
données ne sont alors pas publiées et trouvables sur geocat.ch; c’est pourquoi de telles alternatives ne sont pas recommandées.   
72 Dans le cadre de l’actualisation, les informations manquantes concernant les métadonnées optionnelles seront révisées, tout comme la phrase «Si   
vous désirez publier des géodonnées, faites-le via geo.admin.ch». Celle-ci ne vaut que pour les offices fédéraux. Pour tous les autres offices, les mé-  
tadonnées doivent être publiées sur geocat.ch afin de tenir un catalogue de métadonnées centralisé et de permettant ainsi une mise à jour efficace   
de opendata.swiss par moissonnage.   
   

* * *

![](OGD-Leitfaden-V1.07fr-24_1.png)  
   
23    
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
Fig. 3: Processus de publication de géodonnées sur opendata.swiss    
   

* * *

![](OGD-Leitfaden-V1.07fr-25_1.png)  
![](OGD-Leitfaden-V1.07fr-25_2.png)  
![](OGD-Leitfaden-V1.07fr-25_3.png)  
![](OGD-Leitfaden-V1.07fr-25_4.png)  
   
24    
   
Le cheminement décrit exige la propre conservation des données, car opendata.swiss ne saisit «que» les métadon-  
nées (harvesting) et ne conserve pas les données.   
   
**Aperçu des conditions d’utilisation (détails dans le chap[. 4.1.1)](OGD-Leitfaden-V1.07frs.html#15)**   
**Condition d’utili-**  
**Utilisation libre (non **  
**Indication de la source (auteur, **  
**Utilisation **  
**sation **  
**commerciale) **  
**titre et lien vers le jeu de don-**  
**commerciale **  
**nées) **  
Oui   
Recommandée   
Oui   
   
Oui   
Obligatoire   
Oui   
   
Oui   
Recommandée   
Après accord avec le   
fournisseur de données   
   
Oui   
Obligatoire   
Après accord avec le   
fournisseur de données   
   
Tab. 4: Aperçu des conditions d’utilisation actuel es sur opendata.swiss   
   
La condition d’utilisation à choisir est variable et largement diversifiée pour les publications des OGD. Elle est clai-  
rement définie en présence de la colonne spécifique «Utilisation et distribution libres» dans une OGéo, dans l’an-  
nexe des géodonnées de base, comme le prévoit p. ex. le canton de Zurich.   
   
**Aperçu de la responsabilité (détails dans le chap[. 4.1.2)](OGD-Leitfaden-V1.07frs.html#15)**  
•  La clause de non-responsabilité n’est pas défendable juridiquement.   
•  Cependant, la probabilité d’une responsabilité effective est très faible et doit être considérée indépen-  
damment des publications OGD.   
•  Une assurance qualité des géodonnées est recommandée dans tous les cas.   
**   
Aperçu de la protection des données (détails dans le cha[p. 4.1.3)](OGD-Leitfaden-V1.07frs.html#16)**  
•  Les géodonnées peuvent permettre de remonter vers les personnes. La protection des données ne peut   
donc pas être ignorée et el e est ancrée dans le droit de la géoinformation.   
•  Avant la publication de données (OGD ou non), il faut dans tous les cas vérifier si la protection des don-  
nées est respectée.   
•  Même si le niveau d’autorisation d’accès est défini dans la loi, il faut vérifier si la protection des données   
pourrait être violée. Il se peut que la cat. A contienne des données critiques, puisque la répartition des   
autorisations d’accès peut avoir été effectuée avant l’élaboration des MGDM.    
•  Il ne faut pas perdre de vue les progrès des big data et en tenir compte pour toutes les formes d’agréga-  
tion ou l’anonymisation.   
   
**Aperçu des coûts/de la tarification (détails dans le chap[. 4.1.4)](OGD-Leitfaden-V1.07frs.html#17)**  
•  Le but est la gratuité, mais la réalité (politique) en décide parfois autrement.   
•  Les cantons en particulier doivent déterminer si une remise payante des géodonnées s’avère judicieuse,   
en effectuant un calcul des coûts complets.   
   
  
   

* * *

   
25    
   
**   
   
Aperçu du droit d’auteur (détails dans le chap.[ 4.1.5)](OGD-Leitfaden-V1.07frs.html#18)**  
•  Dans la plupart des cas, les questions de droit d’auteur ne sont pas pertinentes pour les géodonnées, no-  
tamment s’il existe des consignes définies pour la saisie ou la représentation.   
•  Dans des cas particuliers, cela peut devenir pertinent, spécialement s’il s’agit de données d’un mandat   
extérieur, comprenant des images ou créées individuel ement.   
•  Une éventuelle violation du droit d’auteur doit donc être vérifiée dans le cadre de la publication d’OGD,   
même si ce sera sans résultat dans la plupart des cas.   
   
**Aperçu des formats et protocoles de données (détails dans le chap.[ 4.2.2)](OGD-Leitfaden-V1.07frs.html#19)**Dans les portails et publications OGD, on distingue en général:   
•  Formats de géodonnées: GeoJSON, KML, GML, INTERLIS, ESRI shape file, GeoPackage, GeoTIFF, gpx, dxf,   
dwg, ecw, wld;   
•  Protocoles d’accès: WMS, WMTS, WFS   
**6.1 **  
**Choix des géodonnées pour les OGD **  
Les géodonnées citées dans une ordonnance sur la géoinformation avec service de téléchargement doivent être   
publiées, mais pas impérativement selon le principe des OGD. Les opportunités et les risques (chap[. 5)](OGD-Leitfaden-V1.07frs.html#21) doivent être   
pris en compte et pondérés pour le choix d’autres géodonnées.   
   
Les géodonnées devant être publiées relèvent fondamentalement de la décision prise à l’échelon supérieur (p. ex.   
responsable politique, direction de l’autorité, responsables des données) et dépendent notamment des points sui-  
vants:   
•  Quelle est la force de l’engagement pour les OGD en général?   
•  Quelle est la volonté des responsables politiques de renoncer, le cas échéant, aux recettes de la vente de   
données avec des efforts identiques?   
•  Quel est l’importance du coût de publication des données selon le principe des OGD?   
•  Où le coût est-il le plus bas pour obtenir rapidement des résultats probants?   
•  Quel es sont les données les plus demandées? Les données sur les liens vers le portail fédéral ou les por-  
tails cantonaux peuvent donner des indications.   
•  Quelles données devraient être publiées pour des raisons d’efficacité (publication unique au lieu de distri-  
bution individuel e répétée)?   
•  Existe-t-il une vue d’ensemble des volumes de données (= inventaire)?   
   
La sélection des données pour la publication des OGD fait l’objet de tensions (Paderta, 2012) p. 5:   
•  Liberté d’information contre protection des données    
•  Nouvelles formes de participation et collaboration contre culture administrative traditionnelle dans le sec-  
teur public   
•  Réutilisation commerciale contre refinancement des Open Government Geo Data.   
   
Les expériences faites montrent qu’une priorisation thématique est moins choisie; on privilégie ici plutôt l’aspect   
pratique: d’abord des géodonnées au niveau d’autorisation d’accès «A», peu de frais de mise à disposition, peu de   
pertes de recettes et utilisation plus large.    
   
  
   

* * *

   
26    
   
**6.2 **  
**Traitement de «données plus anciennes», mise à jour et états temporels **  
Sont ici prioritaires les prescriptions légales (OGéo) sur la disponibilité durable, l’historique et l’archivage ainsi que   
l’étude correspondante du CSI-SIG (disponibilité assurée dans la durée et archivage des géodonnées).    
   
Les entretiens réalisés dans le cadre du présent guide ont montré que fondamentalement des données remontant   
à des dates antérieures devraient rester disponibles, sans que cela soit une obligation (disclaimer). Les entretiens   
ont de plus montré que la publication OGD par la mise à disposition des métadonnées via harvesting pour open-  
data.swiss fonctionne bien[73](OGD-Leitfaden-V1.07frs.html#27).   
   
Si les informations temporel es étaient contenues dans les données el es-mêmes (statistiques de votations p. ex.),   
les données les plus récentes seraient reportées dans le fichier existant et ainsi publiées.   
En général, on n’accorde pas une trop grande importance à cette question, car en principe, ce sont les autorités   
qui déterminent les données publiées, la date de publication et leur état.    
**6.3 **  
**Système d’étoiles pour le label de qualité OGD **  
Habituellement, on utilise le modèle 5 étoiles de Tim Berners-Lee pour il ustrer les critères de qualité des Open   
Data et Linked Data. Les Open Data sont subdivisées en cinq niveaux[74: ](OGD-Leitfaden-V1.07frs.html#27)   
   
★   
Publication de données avec licence ouverte, dans un format quelconque   
★★   
Publication de données dans un format structuré (p. ex. Excel au lieu d’un tableau PDF)   
★★★   
Publication de données dans un format ouvert (p. ex. CSV au lieu d’Excel)   
★★★★   
Utilisation d’identificateurs univoques (URI) pour les entités   
★★★★★   
Mise en lien des données publiées avec d’autres données, afin de créer un contexte   
Les trois premiers niveaux décrivent primairement les Open Data, les deux derniers les Linked Open Data. Le mo-  
dèle 5 étoiles est utile, mais a des faiblesses: les services Web ou les Application Programming Interfaces par   
exemple ne sont pas suffisamment couverts. De plus, il faut être clair: le système Berners-Lee évalue la mise en   
lien et partiellement l’utilité, mais pas la qualité intrinsèque des données.   
**6.4 **  
**Tâches à réaliser pour l’introduction des OGD  **  
Préparation:   
  Existence d’une base légale (droit de la géoinformation, lois spécifiques, etc.)?   
  Autorisation d’accès clarifiée?   
  Service compétent désigné?   
  Cycle d’actualisation et de publication déterminé?   
  Droit de protection des données vérifié?   
  Question du droit d’auteur vérifiée?   
  Question des coûts/émoluments clarifiée?   
  Utilisation commerciale possible?   
  Obligation d’indication de la source des données?   
   
   
73 La classe GM03/ISO19139 «AggregateInformation» (implémentée dans geocat) pourrait mieux représenter les relations entre géodonnées - donc   
aussi les états temporels - mais devrait également être prise en compte dans le modèle d’opendata.swiss; le coût d’utilisation de «AggregateInforma-  
tion» devrait être vérifié.   
74 (opendata.swiss, 2017)   
   

* * *

   
27    
   
Exécution:   
  Unité d’organisation et jeu de données saisis dans geocat.ch (ou un autre catalogue de géométadonnées   
«moissonné» par opendata.swiss, évent. Via geocat.ch)?   
  Métadonnées complétées pour publication OGD?   
  CSW-Endpoint demandé chez geocat.ch?   
  Harvesting du CSW-Endpoint demandé chez opendata.swiss?   
**6.5 **  
**A-t-on besoin d’une loi sur les OGD? **  
Les entretiens n’apportent pas ici de réponse uniforme, révélant même une grande diversité des réponses. Une   
tendance en faveur d’une loi OGD (niveau Confédération) se dégage certes, mais le choix des partenaires intervie-  
wés n’est pas représentatif.   
   
Le consensus majoritaire pourrait être le suivant: une loi OGD ne serait pas nécessaire si les objectifs de la straté-  
gie OGD étaient inclus dans les lois sectorielles spécifiques. Mais il y a là une grande incertitude quant à la faisabi-  
lité et à l’étendue. La stratégie actuelle du Conseil fédéral est généralement perçue comme trop faible pour:   
•  D’une part faire bouger ceux qui ne suivent pas la tendance des OGD,   
•  D’autre part pour justifier politiquement les pertes de recettes qui en résultent.   
   
Arguments pour la loi OGD:   
•  Il faut une base légale contraignante pour la publication OGD (principe de légalité).   
•  La stratégie OGD de Confédération est insuffisante. El e n’est pas contraignante et n’oblige personne à   
participer.   
•  Les pertes de recettes et les ressources résultant d’une loi OGD ne doivent pas de nouveau être défen-  
dues ou justifiées sur le plan politique.   
•  La numérisation est en cours et il ne faut pas passer à côté.   
•  Les lois spécifiques (p. ex. LGéo) pourraient et devraient s’intégrer dans ce contexte.   
•  Espoir de conditions d’utilisation coordonnées pour toute la Suisse   
   
Arguments contre la loi OGD:   
•  Crainte de contradictions avec le droit de la géoinformation   
•  N’est pas perçue comme nécessaire (spécialement par les responsables dont l’action politique constitue   
un soutien marqué pour les OGD).   
   
En dehors de la législation spécifique, les géodonnées pourraient selon (Wiedmer & Seiberth, 2015) être publiées   
selon les bases juridiques suivantes[75](OGD-Leitfaden-V1.07frs.html#28):   
•  Mandat d’information de la Constitution fédérale[76   
](OGD-Leitfaden-V1.07frs.html#28)•  Loi sur l’organisation du gouvernement et de l’administration[77](OGD-Leitfaden-V1.07frs.html#28) Art. 10 et 40   
**6.6 **  
**Qu’en est-il de la certification? **  
La certification d’un service officiel, comme un extrait de cadastre pour une demande de permis de construire, n’a   
pas été perçue par toutes les personnes interviewées comme une fonctionnalité nécessaire d’un portail OGD ou   
   
75 De l’avis des auteures, la loi et l’ordonnance sur la transparence ne pourraient constituer ici qu’une base législative partiel e.   
76 Art. 180, al. 2 CF: «\[Le Conseil fédéral\] renseigne le public sur son activité en temps utile et de manière détail ée, dans la mesure où   
aucun intérêt public ou privé prépondérant ne s’y oppose.»   
77 Art. 10 LOGA: Information sur l’activité du Conseil fédéral; pour les responsabilités, voir aussi art. 10a et 34 ainsi que art. 40 LOGA:   
Le chef de département prend, en accord avec la Chancel erie fédérale, les mesures nécessaires pour informer le public sur l’activité   
de son département; il désigne les responsables de l’information.   
   

* * *

   
28    
   
du processus de publication. Si ce processus existe dans le cadre de la mise à disposition de données, il n’est appa-  
remment pas pertinent pour les OGD et a lieu en dehors de celui-ci.   
**6.7 **  
**Valeurs empiriques/meilleures pratiques **  
Lors des entretiens ainsi que lors de l’enquête CadastreSuisse, les éléments suivants à propos de la publication de   
géodonnées OGD se sont dégagés:   
•  Le rôle de l’État doit être tiré au clair: l’administration met-el e à disposition les données pour l’économie   
privée ou veut-el e proposer el e-même des services à valeur ajoutée?   
•  Du côté de l’administration, est-on prêt à «lâcher prise» et donc à perdre le contrôle de ses «propres»   
données?   
•  L’importance d’un discours actif des offices concernés ainsi que de leur coordination.   
•  Les services sont une possibilité de publier rapidement des géodonnées officiel es sur opendata.swiss. La   
mise à disposition en tant que services a moins d’importance pour les utilisateurs.   
•  Un portail propre a certes des avantages en termes d’autonomie, mais son coût est élevé.   
•  Valeur de la communication de success stories pour la motivation.   
•  Une certaine influence des cantons voisins quant à la volonté d’action politique.   
•  Au total moins de coûts pour l’administration et des coûts légèrement supérieurs pour les tâches tech-  
niques et la documentation.   
•  Les géomètres craignent la perte de tâches et pourraient se montrer sceptiques.   
•  Le souci de perte de revenus est grand, particulièrement en présence de gros clients disposant de plus de   
moyens pécuniaires (surtout des entreprises proches de l’État).   
   
L’Open Knowledge Foundation propose quelques conseils généraux et fait part de son expérience[78: ](OGD-Leitfaden-V1.07frs.html#29)   
•  Commencer petit, avancer par étapes et tirer des enseignements de ses premières expériences.   
•  Intégrer la communauté d’utilisateurs: impliquer précocement les producteurs et consommateurs de don-  
nées.   
•  Repérer rapidement les questions ouvertes et les craintes et y répondre (p. ex. coûts).   
•  Bien réfléchir à la bonne condition d’utilisation qui sera acceptée.   
•  Déterminer la bonne page pour la publication: sa propre page, un portail OGD, etc.   
•  S’agit-il simplement des données à télécharger ou existe-t-il de meil eures solutions plus coûteuses?   
•  Ne pas avoir l’attente d’une publication individuelle - laisser les données se diffuser.   
•  Assurer un accès sur un pied d’égalité: pas de droits d’accès exclusifs.    
   
(Neuroni, Riedl, & Brugger, 2013) sur l’exemple de la ville de Zurich (p. 1917)   
•  La maturité organisationnelle doit être acquise, aussi bien dans l’administration en général que dans les   
domaines spécialisés.    
•  Une implication à grande échelle ralentit le processus, mais augmente la probabilité d’une exécution et   
d’une conclusion fructueuses.   
•  Une gestion des risques active est importante: identifier les risques rapidement et appliquer des mesures   
concrètes pour les minimiser.   
•  Communication active sur le projet, les objectifs, la plus-value et les défis posés.   
•  Des standards communs accroissent l’acceptation globale.   
•  Un commitment politique clair (principe directeur) car on constate entre autres, outre des barrières in-  
ternes, une résistance du côté des parties politiques.   
   
(Durrer, 2017) Concernant un traitement correct des données:   
   
78 (Open Knowledge International, o. J.)   
   

* * *

   
29    
   
•  Lors d’acquisitions régulières de données, un automatisme doit être possible.   
•  Les données doivent être proposées par une API ou d’autres mécanismes simples.   
•  Les liens doivent être stables (et donc bien pensés lors de la conception).   
•  À part les valeurs et l’en-tête (nom de colonne), aucune information ne doit être intégrée dans le fichier,   
sinon la lisibilité par machine n’est pas assurée.   
•  Les définitions de format de fichier, comme les jeux de caractères (UTF-8), sont des informations impor-  
tantes pour que les caractères spéciaux puissent être lus correctement.   
•  Les valeurs manquantes doivent être clairement documentées. Des expressions comme «n.a.» peuvent   
poser problème dans des formats de colonne numériques. «-1» pourrait convenir si on est certain qu’il n’y   
a pas de valeurs négatives.    
•  Pour une utilisation durable des données, il est important que ni le format ni la structure ne changent.   
   
  
   

* * *

   
30    
   
**7. Vue d’ensemble des portails OGD **  
Il existe beaucoup d’accès publics à des informations de la part d’offices - citons les géoportails. Toutefois, les   
OGD posent des exigences plus élevées (voir chap[. 2.2)](OGD-Leitfaden-V1.07frs.html#9).    
   
Parmi les portails OGD, opendata.swiss, projet commun de la Confédération et des cantons, est la plus impor-  
tante plateforme de publication. Actuellement[79,](OGD-Leitfaden-V1.07frs.html#31) on recense plus de 2000 jeux de données venant de 35 or-  
ganisations. De plus, 30 applications montrent ce qui peut être fait avec ces données.   
   
Il existe également le portail OGD de la ville de Zurich [(https://data.stadt-zuerich.ch)](https://data.stadt-zuerich.ch/), qui a été mis en ligne   
quelques années avant opendata.swiss. On dispose ici de 300 jeux de données, dont la plupart utilisables   
sans restrictions. Il existe de plus quelques portails OGD plus petits au niveau cantonal, à l’image de lustat.ch   
(statistiques de Lucerne) ou dans le canton de Bâle-Vil e.    
   
Au plan international, on trouve divers portails supranationaux, nationaux et autres, l’interconnexion grandis-  
sante via les LOD étant ici essentielle.   
**8. Aperçu de l’utilisation des LOD **  
Les LOD sont constituées de RDF interconnectés (sujet-prédicat-objet). Ainsi, le Web «apprend», à l’aide d’expres-  
sions comme «Berne-est\_dans-liste\_des\_capitales» et de «Berne-est\_en-Suisse», que Berne est la capitale de la   
Suisse. Si on intègre que chaque pays n’a qu’une capitale, le Web «apprend» que les autres vil es suisses ne peu-  
vent pas être la capitale.   
   
Le portail de la Confédération propose un Linked Data Endpoint[ (www.geo.admin.ch/linkeddata)](http://www.geo.admin.ch/linkeddata). Celui-ci permet   
des requêtes avec SPARQL, mais pose des exigences pour les données mises à disposition. En service depuis mars   
2017 seulement, plus de 1500 vues/jour ont été enregistrés au bout d’un mois, traduisant donc un intérêt pour   
une interconnexion plus poussée[80.](OGD-Leitfaden-V1.07frs.html#31)   
   
Les Archives fédérales planchent sur une «version LOD» d’opendata.swiss dans le projet LINDAS. Les personnes   
intéressées peuvent se faire une première idée de ce portail pilote sur lindas-data.ch.    
   
(Von Lucke & Geiger, 2010) indiquent quelques exemples de LOD:   
•  DBpedia, Wikipédia en version RDF   
•  GeoNames, qui a saisi plus de 11 mil ions de noms de lieux   
•  EuroStat, qui actualise et complète en permanence les statistiques européennes et qui les met à disposi-  
tion par un SPARQL Endpoint.   
•  Linked GeoData: données Open Street publiées en RDF, également utilisables par un SPARQL Endpoint.    
   
D’autres offres LOD montrent l’importance grandissante de cette technologie pour la constitution du Web séman-  
tique:   
•  À part l’autorité statistique européenne Eurostat, le portail de données de l’UE propose également des   
LOD et un SPARQL Endpoint [(https://data.europa.eu/euodp/fr/linked-data);](https://data.europa.eu/euodp/en/linked-data))   
•  La bibliothèque nationale al emande met sur pied un Linked Data Service pour intégrer dans le Web sé-  
mantique la totalité des connaissances bibliographiques;   
•  En Autriche, le portail LOD public est étendu [(https://www.data.gv.at/linked-data/);](https://www.data.gv.at/linked-data/)) Celui-ci se base égale-  
ment sur RDF et met à disposition un SPARQL Endpoint.   
•  En Italie, une organisation à but non lucratif promeut la mise sur pied d’un portail LOD   
[(http://www.linkedopendata.it/en-home),](http://www.linkedopendata.it/en-home)) en partie avec des géoportails régionaux.      
   
  
   
79 État au 4 mai 2017   
80 En 2018, des Linked Open Data Business Cases doivent être opérationnels dans le canton de Bâle-Vil e(Rol i, 2017).   
   

* * *

   
31    
   
**9. Bibliographie, liens utiles **  
**Bürgi-Schmelz, A. (2013)**. Wirtschaftliche Auswirkungen von Open Government Data. Bern: Schweizerisches Bun-  
desarchiv.   
**Bürgi-Schmelz, A. (2014).**[ OGD Schweiz Abgrenzung zwischen OGD und kundenspezifischen, individuel en Leistun-](https://www.egovernment.ch/index.php/download_file/force/475/3337/)  
[gen.](https://www.egovernment.ch/index.php/download_file/force/475/3337/)   
**Durrer, C. (2017)**[. Datenquel en sol  man nutzen können. ht](http://www.oyatec.ch/2017/04/24/datenquellen-soll-man-nutzen-koennen/)tp://www.oyatec.ch/2017/04/24/datenquellen-sol -  
man-nutzen-koennen/   
**Geiger, C. P., & Von Lucke, J. (2012).** Open government and (linked)(open)(government)(data). JeDEM-eJournal of   
eDemocracy and open Government, 4(2), 265–278.   
**Jörg, W. (2014). **ViennaGIS(R) verschenkt seine Geodaten - Können wir uns das leisten? Vermessung & Geoinfor-  
mation, 3(2014), 138–145.   
**Kettiger, D. (2016, März[). ](http://www.kettiger.ch/fileadmin/user_upload/Dokumente/News/ITSL_160309_Referat_Website_DE.pdf)**[Die rechtliche Situation von «Open Geo Data» in der Schweiz. ](http://www.kettiger.ch/fileadmin/user_upload/Dokumente/News/ITSL_160309_Referat_Website_DE.pdf)Gehalten auf der ITSL Vor-  
abendveranstaltung, Zürich. http://www.kettiger.ch/fileadmin/user\_upload/Dokumente/News/ITSL\_160309_Re-  
ferat\_Website\_DE.pdf   
**Laux, C. (2012)[.](https://www.stadt-zuerich.ch/content/dam/stzh/portal/Deutsch/OGD/Dokumente/OGD-Gutachten_pub.pdf)**[ Haftung der Stadt Zürich für Open Government Data.  ](https://www.stadt-zuerich.ch/content/dam/stzh/portal/Deutsch/OGD/Dokumente/OGD-Gutachten_pub.pdf)https://www.stadt-zuerich.ch/con-  
tent/dam/stzh/portal/Deutsch/OGD/Dokumente/OGD-Gutachten_pub.pdf   
**Neuroni, A. C., Riedl, R., & Brugger, J. (2013).**[ Swiss Executive Authorities on Open Government Data – Policy Ma-](https://doi.org/10.1109/HICSS.2013.19)  
[king beyond Transparency and Participation. I](https://doi.org/10.1109/HICSS.2013.19)n 2013 46th Hawaii International Conference on System Sciences (S.   
1911–1920). https://doi.org/10.1109/HICSS.2013.19   
**OGD Stadt Zürich:[ Werkstatt. (](https://www.stadt-zuerich.ch/portal/de/index/ogd/werkstatt.html)****o. J.)**. https://www.stadt-zuerich.ch/portal/de/index/ogd/werkstatt.html   
**Open Knowledge International. (o. J.)[.](http://opendatahandbook.org/)**[ Open Data Handbook.](http://opendatahandbook.org/) http://opendatahandbook.org   
**opendata.swiss. (2017).**[ OGD Handbook \[Wiki\].](http://handbook.opendata.swiss/de/pages/index) http://handbook.opendata.swiss/de/pages/index   
**opendefinition.org. (2017).**[ The Open Definition.](http://opendefinition.org/) http://opendefinition.org   
**Paderta, D. (2012).**[ Open Data - Raumbezogene Daten.](http://nbn-resolving.de/urn:nbn:de:0168-ssoar-364743) http://nbn-resolving.de/urn:nbn:de:0168-ssoar-364743   
**Rolf H. Weber. (2000). **Rechtlicher Regelungsrahmen von raumbezogenen Daten. Zürich: Schulthess Verlag.   
**Rolli, S. (2017). **Von freien Geodaten zu Open Government Data im Kanton Basel-Stadt. cadastre Fachzeitschrift für   
das schweizerische Katasterwesen, (Nr.23), 18–22.   
**Schweizerischer Bundesrat. (2014).**[ Open-Government-Data-Strategie Schweiz 2014–2018.](https://www.admin.ch/opc/de/federal-gazette/2014/3493.pdf)   
**Seiberth, C., & Wiedmer, A. (2015).**[ OGD Schweiz Rechtliche Grundlagen OGD (Disclaimer).   
](https://www.egovernment.ch/index.php/download_file/force/484/3554/)**Seuß, R. (2015)[.](https://doi.org/10.12902/zfv-0054-2015)**[ Open Geo Data – grenzenlos nutzbar? Z](https://doi.org/10.12902/zfv-0054-2015)eitschrift für Geodäsie, Geoinformation und Landmanage-  
ment, 140. Jg.(2/2015), 63–69. https://doi.org/10.12902/zfv-0054-2015   
**Stadt Zürich. (2012).**[ Städtische Open Government Data-Policy Informatik-Handbuch Policy. ](https://www.stadt-zuerich.ch/content/dam/stzh/portal/Deutsch/OGD/Dokumente/OGD-Policy%20V1.pdf)https://www.stadt-  
zuerich.ch/content/dam/stzh/portal/Deutsch/OGD/Dokumente/OGD-Policy%20V1.pdf   
**Sunlight Foundation. (2014)[.](http://sunlightf.wpengine.com/wp-content/uploads/2016/09/OpenDataGuidelines_v3.pdf)**[ Guidelines for Open Data Policies. ](http://sunlightf.wpengine.com/wp-content/uploads/2016/09/OpenDataGuidelines_v3.pdf)http://sunlightf.wpengine.com/wp-content/up-  
loads/2016/09/OpenDataGuidelines_v3.pdf   
**Tauberer, J. (2017).**[ The annotated 8 Principles of Open Government Data.](https://opengovdata.org/) https://opengovdata.org/   
**Von Lucke, J., & Geiger, C. P. (2010).** Open Government Data - Frei verfügbare Daten des öffentlichen Sektors   
(Gutachten für die Deutsche Telekom AG zur T-City Friedrichshafen). Friedrichshafen: Zeppelin University.   
**Wiedmer, A., & Seiberth, C. (2015).**[ OGD Schweiz Konzept: Rechtliche Rahmenbedingungen zur Publikation von ](http://handbook.opendata.swiss/de/library/konzept-rechtliche-rahmen)  
[Daten als Open Government Data (OGD).   
](http://handbook.opendata.swiss/de/library/konzept-rechtliche-rahmen)   
   

* * *

Document Outline
================

*   [1\. Introduction et but](OGD-Leitfaden-V1.07frs.html#7)
    *   [1.1 Situation de départ](OGD-Leitfaden-V1.07frs.html#7)
    *   [1.2 Objectifs et public cible](OGD-Leitfaden-V1.07frs.html#7)
    *   [1.3 Contenu et structure](OGD-Leitfaden-V1.07frs.html#8)
    *   [1.4 Gestion du cycle de vie du document](OGD-Leitfaden-V1.07frs.html#8)
*   [2\. Notions relatives à l’Open Data](OGD-Leitfaden-V1.07frs.html#9)
    *   [2.1 Open Data](OGD-Leitfaden-V1.07frs.html#9)
    *   [2.2 Open Government Data (OGD)](OGD-Leitfaden-V1.07frs.html#9)
    *   [2.3 Linked Open Data](OGD-Leitfaden-V1.07frs.html#10)
    *   [2.4 Conséquences et résumé](OGD-Leitfaden-V1.07frs.html#10)
*   [3\. Notions relatives au droit de la géoinformation (LGéo, OGéo)](OGD-Leitfaden-V1.07frs.html#11)
*   [4\. Concordance entre les OGD et le droit de la géoinformation, applicabilité des OGD pour les géodonnées](OGD-Leitfaden-V1.07frs.html#13)
    *   [4.1 Conditions légales](OGD-Leitfaden-V1.07frs.html#15)
        *   [4.1.1 Conditions d’utilisation](OGD-Leitfaden-V1.07frs.html#15)
        *   [4.1.2 Responsabilité](OGD-Leitfaden-V1.07frs.html#15)
        *   [4.1.3 Protection des données](OGD-Leitfaden-V1.07frs.html#16)
        *   [4.1.4 Coûts/fixation des tarifs](OGD-Leitfaden-V1.07frs.html#17)
        *   [4.1.5 Droit d’auteur](OGD-Leitfaden-V1.07frs.html#18)
    *   [4.2 Conditions techniques](OGD-Leitfaden-V1.07frs.html#19)
        *   [4.2.1 Lisibilité par machine](OGD-Leitfaden-V1.07frs.html#19)
        *   [4.2.2 Formats et protocoles d’accès](OGD-Leitfaden-V1.07frs.html#19)
    *   [4.3 Big data et conséquences](OGD-Leitfaden-V1.07frs.html#20)
*   [5\. Opportunités et risques des OGD](OGD-Leitfaden-V1.07frs.html#21)
    *   [5.1 Opportunités et possibilités](OGD-Leitfaden-V1.07frs.html#21)
    *   [5.2 Risques](OGD-Leitfaden-V1.07frs.html#22)
*   [6\. Le lancement pratique des OGD](OGD-Leitfaden-V1.07frs.html#23)
    *   [6.1 Choix des géodonnées pour les OGD](OGD-Leitfaden-V1.07frs.html#26)
    *   [6.2 Traitement de «données plus anciennes», mise à jour et états temporels](OGD-Leitfaden-V1.07frs.html#27)
    *   [6.3 Système d’étoiles pour le label de qualité OGD](OGD-Leitfaden-V1.07frs.html#27)
    *   [6.4 Tâches à réaliser pour l’introduction des OGD](OGD-Leitfaden-V1.07frs.html#27)
    *   [6.5 A-t-on besoin d’une loi sur les OGD?](OGD-Leitfaden-V1.07frs.html#28)
    *   [6.6 Qu’en est-il de la certification?](OGD-Leitfaden-V1.07frs.html#28)
    *   [6.7 Valeurs empiriques/meilleures pratiques](OGD-Leitfaden-V1.07frs.html#29)
*   [7\. Vue d’ensemble des portails OGD](OGD-Leitfaden-V1.07frs.html#31)
*   [8\. Aperçu de l’utilisation des LOD](OGD-Leitfaden-V1.07frs.html#31)
*   [9\. Bibliographie, liens utiles](OGD-Leitfaden-V1.07frs.html#32)
