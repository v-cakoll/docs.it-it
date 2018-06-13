---
title: Cenni preliminari sulla grafica tridimensionale
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 6d44f27ccd82d535436be03092c3864e3155d1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558317"
---
# <a name="3-d-graphics-overview"></a>Cenni preliminari sulla grafica tridimensionale
<a name="introduction"></a> La funzionalità [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consente agli sviluppatori di creare, trasformare e animare grafica 3D nel markup e nel codice procedurale. Gli sviluppatori possono combinare grafica [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] e [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] per creare controlli dettagliati, realizzare illustrazioni complesse di dati o migliorare l'esperienza utente dell'interfaccia di un'applicazione. Il supporto [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non è progettato come piattaforma per lo sviluppo di giochi con funzionalità complete. Questo argomento contiene cenni preliminari sulla funzionalità di [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] nel sistema grafico di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
 
  
<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>Grafica tridimensionale in un contenitore bidimensionale  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] il contenuto nel grafico [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incapsulato in un elemento, <xref:System.Windows.Controls.Viewport3D>, che può far parte della struttura dell'elemento bidimensionale. Il sistema grafico considera <xref:System.Windows.Controls.Viewport3D> come un elemento visivo bidimensionale come molti altri in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D> funziona come una finestra, ovvero un riquadro di visualizzazione, ovvero in una scena tridimensionale. Più precisamente, si tratta di una superficie sulla quale viene proiettata una scena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 In una tradizionale [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] applicazione, utilizzare <xref:System.Windows.Controls.Viewport3D> come qualsiasi altro elemento contenitore come griglia o area di disegno.  Sebbene sia possibile utilizzare <xref:System.Windows.Controls.Viewport3D> con altri [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] oggetti nello stesso grafico, non è possibile inserire [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] e [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] oggetti all'interno di un <xref:System.Windows.Controls.Viewport3D>.  Questo argomento verrà illustrato come disegnare [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] grafica all'interno di <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>Spazio delle coordinate tridimensionali  
 Il sistema di coordinate [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la grafica [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] individua l'origine nella parte superiore sinistra dell'area di rendering, in genere lo schermo. Nel sistema [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] i valori positivi dell'asse x procedono verso destra, mentre i valori positivi dell'asse y procedono in direzione discendente.  Nel sistema di coordinate [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] l'origine viene individuata invece al centro dell'area di rendering, con i valori positivi dell'asse x che procedono verso destra, i valori positivi dell'asse y che procedono verso l'alto e i valori positivi dell'asse z che procedono verso l'esterno dell'origine, in direzione del visualizzatore.  
  
 ![Sistemi di coordinate](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem-1")  
Rappresentazioni convenzionali dei sistemi di coordinate bidimensionali e tridimensionali  
  
 Lo spazio definito da tali assi è il fotogramma di riferimento fisso per oggetti [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Quando si compilano modelli in questo spazio e si creano luci e fotocamere per visualizzarli, è consigliabile distinguere il fotogramma di riferimento fisso, o "spazio globale", da quello di riferimento locale creato per ogni modello quando si applicano trasformazioni. Si ricordi anche che gli oggetti dello spazio globale possono avere un aspetto completamente diverso o non essere completamente visibili, a seconda delle impostazioni di luce e fotocamera e che la posizione della fotocamera tuttavia non modifica la posizione degli oggetti nello spazio globale.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Fotocamere e proiezioni  
 Gli sviluppatori che usano [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] sono abituati a posizionare le primitive del disegno su uno schermo bidimensionale. Quando si crea una scena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], è importante ricordare che in realtà si crea una rappresentazione [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] di oggetti [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]. Poiché l'aspetto di una scena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] è diverso a seconda del punto di vista dell'osservatore, è necessario specificare tale punto di vista. Il <xref:System.Windows.Media.Media3D.Camera> classe consente di specificare il punto di vista per un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] scena.  
  
 Per comprendere la modalità di rappresentazione di una scena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] su una superficie [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] è anche possibile descrivere la scena come proiezione sulla superficie di visualizzazione. Il <xref:System.Windows.Media.Media3D.ProjectionCamera> consente di specificare proiezioni diverse e le relative proprietà per modificare la modalità di spettatore [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] modelli. Oggetto <xref:System.Windows.Media.Media3D.PerspectiveCamera> specifica una proiezione che rappresenta uno scorcio della scena.  In altre parole, il <xref:System.Windows.Media.Media3D.PerspectiveCamera> offre la prospettiva del punto di fuga.  È possibile specificare la posizione della fotocamera nello spazio delle coordinate della scena, la direzione e il campo visivo per la fotocamera, nonché un vettore che definisce la direzione verso l'alto nella scena. Il diagramma seguente illustra il <xref:System.Windows.Media.Media3D.PerspectiveCamera>della proiezione.  
  
 Il <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> e <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> le proprietà di <xref:System.Windows.Media.Media3D.ProjectionCamera> limitare l'intervallo della proiezione della camera. Poiché le fotocamere possono trovarsi in qualsiasi punto della scena, è possibile che la fotocamera venga posizionata all'interno di un modello o accanto al modello stesso, rendendo difficile distinguere in modo corretto gli oggetti.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> Consente di specificare una distanza minima tra la camera e oltre il quale non verranno disegnati oggetti.  Al contrario, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> consente di specificare una distanza tra la camera oltre la quale non verranno disegnati oggetti, che assicura che gli oggetti troppo lontani riconoscibile non verranno incluse nella scena.  
  
 ![Impostazione della fotocamera](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem-6")  
Posizione della fotocamera  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> Specifica una proiezione ortogonale di un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] del modello a un [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] visiva. In modo analogo ad altre fotocamere, l'oggetto specifica una posizione, una direzione di visualizzazione e una direzione verso l'alto. A differenza di <xref:System.Windows.Media.Media3D.PerspectiveCamera>, tuttavia, <xref:System.Windows.Media.Media3D.OrthographicCamera> descrive una proiezione che non include prospettica. In altre parole, <xref:System.Windows.Media.Media3D.OrthographicCamera> descrive un riquadro di visualizzazione, i cui lati sono paralleli, anziché uno cui lati incontrano in un punto in corrispondenza della fotocamera. La figura seguente mostra lo stesso modello visualizzato tramite <xref:System.Windows.Media.Media3D.PerspectiveCamera> e <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Proiezione ortografica e prospettica](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera_projections4")  
Proiezioni prospettiche e ortografiche  
  
 Il codice seguente illustra alcune impostazioni tipiche della fotocamera.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Modello e primitive mesh  
  
 <xref:System.Windows.Media.Media3D.Model3D> è la classe basa astratta che rappresenta un tipo generico [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] oggetto. Per compilare un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] scena, è necessario visualizzare alcuni oggetti e gli oggetti che costituiscono il grafico della scena derivano da <xref:System.Windows.Media.Media3D.Model3D>. Attualmente, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta modellazione geometrie con <xref:System.Windows.Media.Media3D.GeometryModel3D>. Il <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di questo modello accetta una primitiva mesh.  
  
 Per compilare un modello, iniziare a compilare una primitiva (o mesh). Una primitiva [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] è una raccolta di vertici che costituiscono una sola entità [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]. La maggior parte dei sistemi [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] offre primitive modellate sulla figura chiusa più semplice, ovvero un triangolo definito da tre vertici.  Poiché i tre punti di un triangolo sono complanari, è possibile continuare ad aggiungere triangoli per modellare forme più complesse, denominate mesh.  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] sistema fornisce attualmente il <xref:System.Windows.Media.Media3D.MeshGeometry3D> (classe), che consente di specificare qualsiasi geometria; non supporta attualmente predefiniti [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitive, ad esempio i campi e form cubica. Iniziare a creare un <xref:System.Windows.Media.Media3D.MeshGeometry3D> specificando un elenco di vertici di triangolo come relativo <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> proprietà. Ogni vertice è specificato come un <xref:System.Windows.Media.Media3D.Point3D>.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] specificare questa proprietà come elenco di numeri in gruppi di tre che rappresentano le coordinate di ogni vertice. A seconda della geometria, la mesh potrebbe essere composta da molti triangoli, alcuni dei quali condividono gli stessi angoli (vertici). Per disegnare la mesh in modo corretto, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono necessarie informazioni sui vertici condivisi e sui triangoli che li condividono. Fornire queste informazioni specificando un elenco di indici di triangoli con il <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> proprietà. L'ordine in cui i punti specificati in questo elenco viene specificato il <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco determinerà un triangolo.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Nell'esempio precedente, il <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco specifica otto vertici per definire una mesh a forma di cubo. Il <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> proprietà specifica un elenco di dodici gruppi di tre indici.  Ogni numero nell'elenco fa riferimento a un offset nel <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco.  Ad esempio, i primi tre vertici specificati dal <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco sono (1,1,0), (0, 1,0) e (0, 0,0). I primi tre indici specificati dal <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> elenco sono 0, 2 e 1, che corrispondono al primo, terzo e secondo punti il <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco. Il primo triangolo che costituisce il modello di cubo sarà pertanto composto da (1,1,0) a (0,1,0) a (0,0,0) e gli undici triangoli rimanenti vengono determinati in modo analogo.  
  
 È possibile continuare a definire il modello specificando i valori per il <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> e <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> proprietà.  Per eseguire il rendering della superficie del modello, è necessario che il sistema grafico disponga delle informazioni per stabilire la direzione verso cui è rivolta la superficie in corrispondenza di tutti i triangoli specificati. Tali informazioni consentono al sistema di eseguire calcoli di illuminazione per il modello, con le superfici rivolte direttamente verso una sorgente di luce più brillanti rispetto a quelle con angolazione rispetto alla luce. Sebbene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sia in grado di determinare i vettori normali predefiniti usando le coordinate di posizione, è anche possibile specificare vettori normali diversi per avvicinarsi all'aspetto delle superfici curve.  
  
 Il <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> proprietà specifica una raccolta di <xref:System.Windows.Point>che fornisce al sistema grafico come mappare le coordinate che determinano il modo in cui viene disegnata una trama sui vertici della mesh. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> vengono specificati come un valore compreso tra 0 e 1 inclusi.  Come con la <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> proprietà, il sistema grafico può calcolare per impostazione predefinita le coordinate di trama, ma è possibile scegliere di impostare le coordinate di trama diverse per controllare il mapping di una trama che include parte di un criterio di ripetizione, ad esempio. Per altre informazioni sulle coordinate di trama, vedere gli argomenti successivi oppure Managed Direct3D SDK.  
  
 L'esempio seguente illustra come creare una faccia del modello di cubo in codice procedurale. Si noti che è possibile disegnare l'intero cubo come oggetto GeometryModel3D singolo. Questo esempio disegna la faccia del cubo come modello distinto per applicare in un secondo momento trame separate a ogni faccia.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>Applicazione di classi Material al modello  
  
 Affinché assuma l'aspetto di oggetto tridimensionale, è necessario che a una mesh venga applicata una trama per coprire la superficie definita dai relativi vertici e triangoli, in modo che possa essere illuminata e proiettata dalla fotocamera. In [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], si utilizza la <xref:System.Windows.Media.Brush> classe per applicare colori, modelli, sfumature o altro contenuto visivo alle aree dello schermo.  L'aspetto degli oggetti [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], tuttavia, è una funzione del modello di illuminazione, non solo del colore o dello schema applicato. Gli oggetti reali riflettono la luce in modo diverso in base alla qualità delle superfici. Le superfici lucide e brillanti non presentano infatti lo stesso aspetto delle superfici grezze o opache e alcuni oggetti sembrano assorbire la luce, mentre altri la riflettono. È possibile applicare agli oggetti [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] gli stessi pennelli applicabili agli oggetti [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], anche se non direttamente.  
  
 Per definire le caratteristiche della superficie di un modello, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza la <xref:System.Windows.Media.Media3D.Material> classe astratta. Le sottoclassi concrete della classe Material determinano alcune caratteristiche di aspetto della superficie del modello e a ognuna è associata anche una proprietà Brush a cui è possibile passare un oggetto SolidColorBrush, TileBrush o VisualBrush.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial> Specifica che il pennello verrà applicato al modello come se tale modello sono stati illuminato in modo diffuso. L'uso di DiffuseMaterial è simile all'uso diretto di pennelli su modelli [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]. Le superfici dei modelli non riflettono luce come se fossero brillanti.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial> Specifica che il pennello verrà applicato al modello come se fosse la superficie del modello in grado di riflettere le evidenziazioni di disco rigido o lucente. È possibile impostare il grado di qualità riflettente, o "lucentezza", la trama, specificando un valore per il <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> proprietà.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial> Consente di specificare che la trama verrà applicata come se il modello emettesse una luce uguale al colore del pennello. In questo modo il modello non viene trasformato in luce ma partecipa in modo diverso all'applicazione di ombreggiatura rispetto a quanto accade nel caso di trama applicata con DiffuseMaterial o SpecularMaterial.  
  
 Per prestazioni ottimali, le facce posteriori di un <xref:System.Windows.Media.Media3D.GeometryModel3D> (le facce che non sono visualizzate perché sono sul lato opposto del modello dalla fotocamera) vengono rimosse dalla schermata.  Per specificare un <xref:System.Windows.Media.Media3D.Material> per applicare a faccia posteriore di un modello come un piano, impostare il modello <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà.  
  
 Per ottenere alcune qualità della superficie, ad esempio l'effetto alone o riflettente, è necessario applicare a un modello più pennelli diversi in successione. È possibile applicare e riutilizzare più materiali tramite la <xref:System.Windows.Media.Media3D.MaterialGroup> classe. Gli elementi figlio di MaterialGroup vengono applicati dal primo all'ultimo in più passaggi di rendering.  
  
 Gli esempi di codice seguenti illustrano come applicare un colore a tinta unita e un disegno come pennelli ai modelli [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Illuminazione della scena  
 Nella grafica [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] le luci hanno la stessa funzione delle luci reali, ovvero rendono visibili le superfici. Più precisamente, le luci determinano la parte di scena che viene inclusa nella proiezione. Gli oggetti luce in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creano una varietà di luci e di effetti di ombreggiatura e sono modellati in base al comportamento di varie luci reali. È necessario includere almeno una luce nella scena, altrimenti non sarà visibile alcun modello.  
  
 Luci seguenti derivano dalla classe di base <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: Fornisce illuminazione che si accende tutti gli oggetti in modo uniforme indipendentemente dalla loro posizione orientamento.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: Si accende, ad esempio una sorgente di luce distante.  Le luci direzionali hanno un <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> specificato come un Vector3D, ma nessun percorso specificato.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: Si accende, ad esempio una sorgente di luce nelle vicinanze. Agli oggetti PointLights è associata una posizione dalla quale proiettano la luce. Gli oggetti nella scena vengono illuminati in base alla posizione e alla distanza rispetto alla luce. <xref:System.Windows.Media.Media3D.PointLightBase> espone un <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> proprietà, che determina una distanza oltre il quale i modelli non verranno illuminati dalla luce. PointLight espone anche proprietà di attenuazione che determinano come l'intensità della luce diminuisce a distanza. Per l'attenuazione della luce, è possibile specificare interpolazioni costanti, lineari o quadratiche.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: Eredita da <xref:System.Windows.Media.Media3D.PointLight>. Gli oggetti Spotlight illuminano come gli oggetti PointLight, dispongono di posizione e direzione Proiettano luce in un'area conica impostazione <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> e <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> proprietà, espresso in gradi.  
  
 Le luci sono <xref:System.Windows.Media.Media3D.Model3D> oggetti, pertanto è possibile trasformare e animare le proprietà, tra cui posizione, colore, alla direzione e intervallo.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>Trasformazione di modelli  
 Quando vengono creati, i modelli hanno una determinata posizione nella scena. Per spostare i modelli nella scena, ruotarli o modificarne la dimensione, non è pratico modificare i vertici che li definiscono,  ma è opportuno invece applicare trasformazioni ai modelli, come nel sistema [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)].  
  
 Ogni oggetto modello dispone di un <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà con cui è possibile spostare, orientare nuovamente o ridimensionare il modello.  Quando si applica una trasformazione, si esegue in effetti l'offset di tutti i punti del modello in base a qualsiasi vettore o valore specificato dalla trasformazione. In altre parole, viene trasformato lo spazio delle coordinate in cui il modello è definito ("spazio modello"), ma non vengono modificati i valori che costituiscono la geometria del modello nel sistema di coordinate dell'intera scena ("spazio globale").  
  
 Per altre informazioni sulla trasformazione di modelli, vedere [Cenni preliminari sulle trasformazioni tridimensionali](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Animazione di modelli  
 L'implementazione [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fa parte dello stesso sistema di temporizzazione e animazione della grafica [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]. In altre parole, per animare una scena tridimensionale, è necessario animare le proprietà dei relativi modelli. Anche se è possibile animare direttamente proprietà di primitive, in genere è più semplice animare trasformazioni che modificano la posizione o l'aspetto di modelli. Poiché le trasformazioni possono essere applicate a <xref:System.Windows.Media.Media3D.Model3DGroup> oggetti nonché singoli modelli, è possibile applicare un insieme di animazioni a un elemento figlio di un Model3DGroup e un altro set di animazioni a un gruppo di oggetti figlio. È possibile anche realizzare numerosi effetti visivi animando le proprietà di illuminazione della scena. È infine possibile scegliere di animare la proiezione stessa animando la posizione della fotocamera o il campo visivo. Per informazioni di base sul sistema di animazione e di temporizzazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere gli argomenti [Cenni preliminari sulle animazioni](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Cenni preliminari sugli storybard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) e [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Per animare un oggetto in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], creare una sequenza temporale, definire un'animazione (che rappresenti una effettiva modifica del valore di alcune proprietà nel tempo) e specificare la proprietà alla quale applicare l'animazione. Poiché tutti gli oggetti in un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] scena sono elementi figlio di <xref:System.Windows.Controls.Viewport3D>, le proprietà interessate da qualsiasi animazione che si desidera applicare alla scena sono proprietà di proprietà di Viewport3D.  
  
 Si supponga di voler creare un modello in grado di oscillare sul posto. È possibile scegliere di applicare un <xref:System.Windows.Media.Media3D.RotateTransform3D> al modello e animare l'asse di rotazione da un vettore a un altro. L'esempio di codice seguente illustra l'applicazione di un oggetto Vector3DAnimation alla proprietà Axis dell'oggetto Rotation3D della trasformazione, presupponendo che RotateTransform3D sia una delle diverse trasformazioni applicate al modello con un oggetto TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>Aggiungere contenuto tridimensionale alla finestra  
 Per eseguire il rendering della scena, aggiungere modelli e luci a un <xref:System.Windows.Media.Media3D.Model3DGroup>, quindi impostare il <xref:System.Windows.Media.Media3D.Model3DGroup> come il <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> di un <xref:System.Windows.Media.Media3D.ModelVisual3D>. Aggiungere il <xref:System.Windows.Media.Media3D.ModelVisual3D> per il <xref:System.Windows.Controls.Viewport3D.Children%2A> insieme il <xref:System.Windows.Controls.Viewport3D>. Aggiungere fotocamere al <xref:System.Windows.Controls.Viewport3D> impostando il relativo <xref:System.Windows.Controls.Viewport3D.Camera%2A> proprietà.  
  
 Aggiungere infine il <xref:System.Windows.Controls.Viewport3D> alla finestra. Quando il <xref:System.Windows.Controls.Viewport3D> viene incluso come il contenuto di un elemento di layout come area di lavoro, specificare le dimensioni del Viewport3D impostando il relativo <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> proprietà (ereditata da <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Viewport3D>  
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>  
 <xref:System.Windows.Media.Media3D.DirectionalLight>  
 <xref:System.Windows.Media.Media3D.Material>  
 [Panoramica sulle trasformazioni tridimensionali](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)  
 [Ottimizzazione delle prestazioni tridimensionali di WPF](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
