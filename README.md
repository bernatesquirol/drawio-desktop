# flowio - Guia d'usuari

**TL;DR**: creat al PDU de l'AMB, flowio es una eina per crear diagrames jeràrquics per documentar estudis fets amb dades.

- flowio: [https://sourceforge.net/projects/flowio/files/flowio](https://sourceforge.net/projects/flowio/files/flowio)
- flowio-docs: [https://sourceforge.net/projects/flowio/files/flowio-docs/](https://sourceforge.net/projects/flowio/files/flowio-docs/)

## Introducció i objectius

El projecte flowio s'ha creat al Pla Director Urbanístic ([PDU](urbanisme.amb.cat)), dins l'Àrea Metropolitana de Barcelona ([AMB](www.amb.cat)), per tal de millorar la comunicació, l'eficiència i la integritat dels estudis realitzats amb dades.

Quan es fan estudis amb dades cal tractar-les prèviament, mesclar-les amb altres fonts de dades, i modificar-les fins a obtenir un resultat d'on se'n pugui treure conclusions. Això genera una complexitat si es fan molts estudis amb moltes dades diferents que pot desencadenar repetició de la feina, pèrdua de dades i ineficiència.

L'objectiu principal d'aquest projecte és crear una estructura d'informació per controlar tot aquest flux de dades, per tal que els estudis basats en aquestes siguin replicables, fàcils de comunicar, modulars i transparents. Aquesta estructura consisteix en una una sèrie de diagrames que emmagatzemen totes les metadades i les modificacions que els hi hem fent.

Sovint, les funcions que creem per un estudi són útils per un altre estudi. També utilitzem les dades resultants d'estudis fets prèviament per fer nous estudis, creuant-les amb dades noves. És per això que aquesta eina pot ser útil ja que permet establir aquestes connexions entre diferents bases de dades, estudis o funcions.

Flowio extén l'aplicatiu per Windows que ofereix [draw.io](www.draw.io), que és una pàgina web de codi obert per fer diagrames. El codi de flowio és igualment obert i d'ús públic.

## Instruccions

#### Primers passos

Cal descarregar-se el programa desde aquest [enllaç](https://sourceforge.net/projects/flowio/files/flowio/) i executar-lo en un ordinador Windows.

⚠⚠⚠⚠ 

Atenció!!! El primer cop que s'obra el programa, cal decidir una carpeta on es guardaran tots els diagrames que formin part de l'entorn flowio. Per fer això cal anar a flow.io > Change diagrams folder i seleccionar la carpeta desitjada.![url-params](.\doc\url-params.png) 

⚠⚠⚠⚠

#### Interfície d'usuari

![Sin título-3](.\doc\UI-drawio.png)

La UI de drawio és senzilla, consta de 3 parts:

1. Llibreries de drawio: d'aquí apareixen les formes (blocs) útils per crear diagrames.
2. Espai de treball: Aquí és on es treballa, s'arrosseguen els blocs de 1 i es canvia el text i es connecten amb altres elements mitjançant fletxes.
3. Propietats de la forma: aquesta vista ens permet editar les propietats d'una forma seleccionada a 2

La UI de flowio és exactament igual però a 1 només hi trobem certes llibreries:

- flowio: aquesta llibreria conté els *diagrames standard* que explicarem a continuació.

- diagrames ja creats: cada diagrama guardat es converteix en un bloc que podem enllaçar als nous diagrames

#### Com funciona?

L'usuari ha de crear diagrames que representin els estudis, bases de dades o funcions que s'han executat.

⚠⚠⚠⚠

ATENCIÓ!! Per crear diagrames nous és molt important començar amb File > New, no s'han de crear ni copiant i enganxant un diagrama ja creat, ni esborrant un diagrama ja existent i fent Save as.... Si es fa això el diagrama no estarà identificat únicament i generarà molts problemes.

⚠⚠⚠⚠

Totes les dades es generen a partir dels diagrames. Hi ha uns *diagrames standard* a la llibreria flowio creats com a base d'on crear diagrames.![flowio-lib](.\doc\flowio-lib.png)

Hi ha tres tipus de *diagrames standard* que podem fer:

- Bases de dades: representa el concepte de d'una base de dades original, donada per algú, i no en som responsables del manteniment.

- Funcions: representa el concepte de d'una funció, amb uns paràmetres d'entrada i uns de sortida. Podria ser una funció de Python o una funció de l'ArcGIS

- Estudis: agafen bases de dades i les connecten amb funcions per tal de crear noves dades derivades, que seran el resultat de l'estudi.

Els tres tipus de diagrames tenen una sèrie de blocs que son purament informatius, on hi va un text: títol, descripció,... Tenen els tres també una caixa on hi posa 'Forma versió minificada'. Si es substitueix la forma de dins aquest recuadre per qualsevol altra forma de les llibreries (estan amagades es pot fer click a 'More shapes...'), la versió minificada d'aquella funció, base de dades o estudi .

Els estudis i les funcions tenen una part esquemàtica, que és on s'explica mitjançant diagrames quin procés intern té aquell estudi o funció. Allà és on es pot fer referència a funcions, diagrames o bases de dades de la llibreria. 

Les funcions només poden fer referència a altres funcions, ja que una funció és independent al valor dels seus paràmetres. Els estudis en canvi poden fer referència a bases de dades o altres estudis, d'on surt la informació, i funcions que la transformin.

⚠⚠⚠⚠

Atenció!! al guardar el diagrama és important guardar-lo amb l'extensió .drawio (es fa automàticament). Sinó no es mostrarà com a llibreria

⚠⚠⚠⚠

## Aplicacions

El fet de tenir tots els estudis interrelacionat físicament (els diagrames fan referència explícita als altres diagrames associats) permet crear aplicacions a sobre útils:

- Extensió d'un diagrama

  Aquesta aplicació està incorporada a dins de flow.io i és per visualitzar tota aquesta informació d'una forma més compacte. El que es pot fer és crear un nou diagrama amb tota la informació d'una funció/estudi i la informació dels estudis, funcions o bases de dades que fa referència i així recursivament. Això ens deixa un mapa genèric d'un estudi en concret

  Si es va a flow.io > Expand diagram

![expand-diagram](.\doc\expand-diagram.png)

- flowio-docs

  Aquesta aplicació es tracta d'una aplicació externa de flowio. Flowio-docs crea una documentació basada en els diagrames amb totes les funcions i estudis que hem anat creant. Es pot descarregar desde aquest a través d'aquest [enllaç](https://sourceforge.net/projects/flowio/files/flowio-docs/).