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
ms.openlocfilehash: 725a6dc8e4b4a7b474a7dd85c87cdedd93ba09c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186955"
---
# <a name="3-d-graphics-overview"></a>Cenni preliminari sulla grafica tridimensionale
<a name="introduction"></a>La funzionalità 3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in consente agli sviluppatori di disegnare, trasformare e animare grafica 3D sia nel markup che nel codice procedurale. Gli sviluppatori possono combinare grafica 2D e 3D per creare controlli avanzati, fornire illustrazioni complesse di dati o migliorare l'esperienza utente dell'interfaccia di un'applicazione. Il supporto 3D non [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è progettato per fornire una piattaforma di sviluppo di giochi completa. In questo argomento viene fornita una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] panoramica delle funzionalità 3D del sistema grafico.  

<a name="threed_in_2d"></a>
## <a name="3-d-in-a-2-d-container"></a>Grafica tridimensionale in un contenitore bidimensionale  
 Il contenuto grafico [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D in è <xref:System.Windows.Controls.Viewport3D>incapsulato in un elemento, , che può partecipare alla struttura dell'elemento bidimensionale. Il sistema grafico <xref:System.Windows.Controls.Viewport3D> tratta come un elemento visivo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bidimensionale come molti altri in . <xref:System.Windows.Controls.Viewport3D>funziona come una finestra, ovvero una finestra, in una scena tridimensionale. Più precisamente, si tratta di una superficie sulla quale viene proiettata una scena tridimensionale.  
  
 In un'applicazione 2D <xref:System.Windows.Controls.Viewport3D> convenzionale, usare come si farebbe con un altro elemento contenitore come Grid o Canvas.In a conventional 2-D application, use as you would another container element like Grid or Canvas.  Sebbene sia <xref:System.Windows.Controls.Viewport3D> possibile utilizzare con altri oggetti di disegno 2D nello stesso grafico di scena, non è possibile interpenetrare gli oggetti 2D e 3D all'interno di un <xref:System.Windows.Controls.Viewport3D>oggetto .  Questo argomento si concentrerà su come disegnare <xref:System.Windows.Controls.Viewport3D>grafica 3D all'interno del file .  
  
<a name="coord_space"></a>
## <a name="3-d-coordinate-space"></a>Spazio delle coordinate tridimensionali  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di coordinate per la grafica 2D individua l'origine nella parte superiore sinistra dell'area di rendering (in genere lo schermo). Nel sistema bidimensionale i valori positivi dell'asse x procedono verso destra, mentre i valori positivi dell'asse y procedono in direzione discendente.  Nel sistema di coordinate 3D, tuttavia, l'origine si trova al centro dell'area di rendering, con i valori positivi dell'asse x che procedono verso destra, ma i valori positivi dell'asse y procedono invece verso l'alto e i valori positivi dell'asse z procedono verso l'esterno dall'origine , verso il visualizzatore.  
  
 ![Sistemi di coordinate](./media/coordsystem-1.png "CoordSystem-1")  
Rappresentazioni convenzionali dei sistemi di coordinate bidimensionali e tridimensionali  
  
 Lo spazio definito da tali assi è il fotogramma di riferimento fisso per oggetti tridimensionali in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Quando si compilano modelli in questo spazio e si creano luci e fotocamere per visualizzarli, è consigliabile distinguere il fotogramma di riferimento fisso, o "spazio globale", da quello di riferimento locale creato per ogni modello quando si applicano trasformazioni. Si ricordi anche che gli oggetti dello spazio globale possono avere un aspetto completamente diverso o non essere completamente visibili, a seconda delle impostazioni di luce e fotocamera e che la posizione della fotocamera tuttavia non modifica la posizione degli oggetti nello spazio globale.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Fotocamere e proiezioni  
 Gli sviluppatori che lavorano in 2D sono abituati a posizionare le primitive di disegno su uno schermo bidimensionale. Quando si crea una scena 3D, è importante ricordare che si sta realmente creando una rappresentazione 2D di oggetti 3D. Poiché una scena 3D ha un aspetto diverso a seconda del punto di vista dello osservatore, è necessario specificare tale punto di vista. La <xref:System.Windows.Media.Media3D.Camera> classe consente di specificare questo punto di vista per una scena 3D.  
  
 Un altro modo per comprendere come viene rappresentata una scena 3D su una superficie 2D consiste nel descrivere la scena come proiezione sulla superficie di visualizzazione. Consente <xref:System.Windows.Media.Media3D.ProjectionCamera> di specificare proiezioni diverse e le relative proprietà per modificare il modo in cui lo osservatore vede i modelli 3D. A <xref:System.Windows.Media.Media3D.PerspectiveCamera> specifica una proiezione che accorcia la scena.  In altre parole, la <xref:System.Windows.Media.Media3D.PerspectiveCamera> prospettiva fornisce punto di fuga.  È possibile specificare la posizione della fotocamera nello spazio delle coordinate della scena, la direzione e il campo visivo per la fotocamera, nonché un vettore che definisce la direzione verso l'alto nella scena. Il diagramma seguente <xref:System.Windows.Media.Media3D.PerspectiveCamera>illustra la proiezione.  
  
 Le <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> proprietà <xref:System.Windows.Media.Media3D.ProjectionCamera> e di limitare l'intervallo di proiezione della fotocamera. Poiché le fotocamere possono trovarsi in qualsiasi punto della scena, è possibile che la fotocamera venga posizionata all'interno di un modello o accanto al modello stesso, rendendo difficile distinguere in modo corretto gli oggetti.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>consente di specificare una distanza minima dalla fotocamera oltre la quale gli oggetti non verranno disegnati.  Al contrario, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> consente di specificare una distanza dalla fotocamera oltre la quale gli oggetti non verranno disegnati, in modo da garantire che gli oggetti troppo lontani per essere riconoscibili non vengano inclusi nella scena.  
  
 ![Impostazione della fotocamera](./media/coordsystem-6.png "CoordSystem-6")  
Posizione della fotocamera  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>specifica una proiezione ortogonale di un modello 3D su una superficie visiva 2D. In modo analogo ad altre fotocamere, l'oggetto specifica una posizione, una direzione di visualizzazione e una direzione verso l'alto. A <xref:System.Windows.Media.Media3D.PerspectiveCamera>differenza <xref:System.Windows.Media.Media3D.OrthographicCamera> di , tuttavia, descrive una proiezione che non include lo scorcio prospettico. In altre <xref:System.Windows.Media.Media3D.OrthographicCamera> parole, descrive un riquadro di visualizzazione i cui lati sono paralleli, invece di uno i cui lati si incontrano in un punto in cui la fotocamera. L'immagine seguente mostra lo <xref:System.Windows.Media.Media3D.PerspectiveCamera> stesso <xref:System.Windows.Media.Media3D.OrthographicCamera>modello visualizzato utilizzando e .  
  
 ![Proiezione ortografica e prospettica](./media/camera-projections4.png "Camera_projections4")  
Proiezioni prospettiche e ortografiche  
  
 Il codice seguente illustra alcune impostazioni tipiche della fotocamera.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Modello e primitive mesh  
  
 <xref:System.Windows.Media.Media3D.Model3D>è la classe base astratta che rappresenta un oggetto 3D generico. Per creare una scena 3D, è necessario che alcuni oggetti vengano visualizzati e gli oggetti che costituiscono il grafico della scena derivino da <xref:System.Windows.Media.Media3D.Model3D>. Attualmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta geometrie di modellazione con <xref:System.Windows.Media.Media3D.GeometryModel3D>. La <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di questo modello accetta una primitiva mesh.  
  
 Per compilare un modello, iniziare a compilare una primitiva (o mesh). Una primitiva 3D è una raccolta di vertici che formano una singola entità 3D. La maggior parte dei sistemi 3D fornisce primitive modellate sulla figura chiusa più semplice: un triangolo definito da tre vertici.  Poiché i tre punti di un triangolo sono complanari, è possibile continuare ad aggiungere triangoli per modellare forme più complesse, denominate mesh.  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema 3D fornisce <xref:System.Windows.Media.Media3D.MeshGeometry3D> attualmente la classe , che consente di specificare qualsiasi geometria; attualmente non supporta primitive 3D predefinite come sfere e forme cubiche. Iniziare a <xref:System.Windows.Media.Media3D.MeshGeometry3D> creare un specificando un elenco <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> di vertici del triangolo come proprietà. Ogni vertice viene <xref:System.Windows.Media.Media3D.Point3D>specificato come oggetto .  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], specificare questa proprietà come elenco di numeri raggruppati in tre che rappresentano le coordinate di ogni vertice. A seconda della geometria, la mesh potrebbe essere composta da molti triangoli, alcuni dei quali condividono gli stessi angoli (vertici). Per disegnare la mesh in modo corretto, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono necessarie informazioni sui vertici condivisi e sui triangoli che li condividono. Queste informazioni vengono fornite specificando un elenco di <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> indici di triangolo con la proprietà. Questo elenco specifica l'ordine in cui <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> i punti specificati nell'elenco determineranno un triangolo.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Nell'esempio precedente, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> l'elenco specifica otto vertici per definire una mesh a forma di cubo. La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> proprietà specifica un elenco di dodici gruppi di tre indici.  Ogni numero nell'elenco fa riferimento <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> a un offset nell'elenco.  Ad esempio, i primi tre <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> vertici specificati dall'elenco sono (1,1,0), (0,1,0) e (0,0,0). I primi tre indici <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> specificati dall'elenco sono 0, 2 e 1, che corrispondono <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> al primo, terzo e secondo punto dell'elenco. Il primo triangolo che costituisce il modello di cubo sarà pertanto composto da (1,1,0) a (0,1,0) a (0,0,0) e gli undici triangoli rimanenti vengono determinati in modo analogo.  
  
 È possibile continuare a definire il <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> modello <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> specificando i valori per le proprietà e .  Per eseguire il rendering della superficie del modello, è necessario che il sistema grafico disponga delle informazioni per stabilire la direzione verso cui è rivolta la superficie in corrispondenza di tutti i triangoli specificati. Tali informazioni consentono al sistema di eseguire calcoli di illuminazione per il modello, con le superfici rivolte direttamente verso una sorgente di luce più brillanti rispetto a quelle con angolazione rispetto alla luce. Sebbene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sia in grado di determinare i vettori normali predefiniti usando le coordinate di posizione, è anche possibile specificare vettori normali diversi per avvicinarsi all'aspetto delle superfici curve.  
  
 La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> proprietà specifica una <xref:System.Windows.Point>raccolta di s che indicano al sistema grafico come mappare le coordinate che determinano come una trama viene disegnata ai vertici della mesh. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>vengono specificati come un valore compreso tra zero e 1, inclusi.  Come per <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> la proprietà, il sistema grafico può calcolare le coordinate di trama predefinite, ma è possibile scegliere di impostare coordinate di trama diverse per controllare il mapping di una trama che include parte di un motivo ripetuto, ad esempio. Per altre informazioni sulle coordinate di trama, vedere gli argomenti successivi oppure Managed Direct3D SDK.  
  
 L'esempio seguente illustra come creare una faccia del modello di cubo in codice procedurale. Si noti che è possibile disegnare l'intero cubo come oggetto GeometryModel3D singolo. Questo esempio disegna la faccia del cubo come modello distinto per applicare in un secondo momento trame separate a ogni faccia.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>
## <a name="applying-materials-to-the-model"></a>Applicazione di classi Material al modello  
  
 Affinché assuma l'aspetto di oggetto tridimensionale, è necessario che a una mesh venga applicata una trama per coprire la superficie definita dai relativi vertici e triangoli, in modo che possa essere illuminata e proiettata dalla fotocamera. In 2D si usa <xref:System.Windows.Media.Brush> la classe per applicare colori, motivi, sfumature o altro contenuto visivo alle aree dello schermo.  L'aspetto degli oggetti 3D, tuttavia, è una funzione del modello di illuminazione, non solo del colore o del motivo applicato. Gli oggetti reali riflettono la luce in modo diverso in base alla qualità delle superfici. Le superfici lucide e brillanti non presentano infatti lo stesso aspetto delle superfici grezze o opache e alcuni oggetti sembrano assorbire la luce, mentre altri la riflettono. È possibile applicare tutti gli stessi pennelli agli oggetti 3D che è possibile applicare agli oggetti 2D, ma non è possibile applicarli direttamente.  
  
 Per definire le caratteristiche della superficie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di <xref:System.Windows.Media.Media3D.Material> un modello, viene utilizzata la classe astratta. Le sottoclassi concrete della classe Material determinano alcune caratteristiche di aspetto della superficie del modello e a ognuna è associata anche una proprietà Brush a cui è possibile passare un oggetto SolidColorBrush, TileBrush o VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>specifica che il pennello verrà applicato al modello come se il modello fosse illuminato in modo diffuso. L'uso di DiffuseMaterial è molto simile all'uso dei pennelli direttamente nei modelli 2D; le superfici del modello non riflettono la luce come se brillasse.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>specifica che il pennello verrà applicato al modello come se la superficie del modello fosse dura o lucida, in grado di riflettere le luci. È possibile impostare il grado in cui la trama suggerirà questa qualità riflettente, o "luce", specificando un valore per la <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> proprietà.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>consente di specificare che la texture verrà applicata come se il modello emettesse luce uguale al colore del pennello. In questo modo il modello non viene trasformato in luce ma partecipa in modo diverso all'applicazione di ombreggiatura rispetto a quanto accade nel caso di trama applicata con DiffuseMaterial o SpecularMaterial.  
  
 Per migliorare le prestazioni, <xref:System.Windows.Media.Media3D.GeometryModel3D> le facce posteriori di un (quelle facce che sono fuori dalla vista perché si trovano sul lato opposto del modello dalla fotocamera) vengono scavate dalla scena.  Per specificare un <xref:System.Windows.Media.Media3D.Material> da applicare alla faccia posteriore di un <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> modello come un piano, impostare la proprietà del modello.  
  
 Per ottenere alcune qualità della superficie, ad esempio l'effetto alone o riflettente, è necessario applicare a un modello più pennelli diversi in successione. È possibile applicare e riutilizzare <xref:System.Windows.Media.Media3D.MaterialGroup> più materiali utilizzando la classe . Gli elementi figlio di MaterialGroup vengono applicati dal primo all'ultimo in più passaggi di rendering.  
  
 Negli esempi di codice seguenti viene illustrato come applicare un colore a tinta unita e un disegno come pennelli ai modelli 3D.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Illuminazione della scena  
 Le luci nella grafica 3D fanno quello che le luci fanno nel mondo reale: rendono visibili le superfici. Più precisamente, le luci determinano la parte di scena che viene inclusa nella proiezione. Gli oggetti luce in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creano una varietà di luci e di effetti di ombreggiatura e sono modellati in base al comportamento di varie luci reali. È necessario includere almeno una luce nella scena, altrimenti non sarà visibile alcun modello.  
  
 Le seguenti luci derivano <xref:System.Windows.Media.Media3D.Light>dalla classe base :  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: fornisce un'illuminazione ambientale che illumina tutti gli oggetti in modo uniforme indipendentemente dalla loro posizione o orientamento.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: si illumina come una fonte di luce distante.  Le luci direzionali hanno un <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> oggetto specificato come Vector3D, ma nessuna posizione specificata.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: si illumina come una fonte di luce vicina. Agli oggetti PointLights è associata una posizione dalla quale proiettano la luce. Gli oggetti nella scena vengono illuminati in base alla posizione e alla distanza rispetto alla luce. <xref:System.Windows.Media.Media3D.PointLightBase>espone una <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> proprietà, che determina una distanza oltre la quale i modelli non saranno illuminati dalla luce. PointLight espone anche proprietà di attenuazione che determinano come l'intensità della luce diminuisce a distanza. Per l'attenuazione della luce, è possibile specificare interpolazioni costanti, lineari o quadratiche.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: eredita <xref:System.Windows.Media.Media3D.PointLight>da . Gli oggetti Spotlight illuminano come gli oggetti PointLight, dispongono di posizione e direzione Proiettano la luce in un'area <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> a forma di cono impostata da e dalle proprietà, specificate in gradi.  
  
 Le <xref:System.Windows.Media.Media3D.Model3D> luci sono oggetti, pertanto è possibile trasformare e animare le proprietà della luce, tra cui posizione, colore, direzione e intervallo.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Trasformazione di modelli  
 Quando vengono creati, i modelli hanno una determinata posizione nella scena. Per spostare i modelli nella scena, ruotarli o modificarne la dimensione, non è pratico modificare i vertici che li definiscono,  ma è opportuno invece applicare trasformazioni ai modelli, come nel sistema bidimensionale.  
  
 Ogni oggetto modello <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> dispone di una proprietà con cui è possibile spostare, riorientare o ridimensionare il modello.  Quando si applica una trasformazione, si esegue in effetti l'offset di tutti i punti del modello in base a qualsiasi vettore o valore specificato dalla trasformazione. In altre parole, viene trasformato lo spazio delle coordinate in cui il modello è definito ("spazio modello"), ma non vengono modificati i valori che costituiscono la geometria del modello nel sistema di coordinate dell'intera scena ("spazio globale").  
  
 Per altre informazioni sulla trasformazione di modelli, vedere [Cenni preliminari sulle trasformazioni tridimensionali](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Animazione di modelli  
 L'implementazione tridimensionale di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fa parte dello stesso sistema di temporizzazione e animazione della grafica bidimensionale. In altre parole, per animare una scena tridimensionale, è necessario animare le proprietà dei relativi modelli. Anche se è possibile animare direttamente proprietà di primitive, in genere è più semplice animare trasformazioni che modificano la posizione o l'aspetto di modelli. Poiché le trasformazioni <xref:System.Windows.Media.Media3D.Model3DGroup> possono essere applicate a oggetti e singoli modelli, è possibile applicare un set di animazioni a un elemento figlio di un Model3DGroup e un altro set di animazioni a un gruppo di oggetti figlio. È possibile anche realizzare numerosi effetti visivi animando le proprietà di illuminazione della scena. È infine possibile scegliere di animare la proiezione stessa animando la posizione della fotocamera o il campo visivo. Per informazioni di base sul sistema di animazione e di temporizzazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere gli argomenti [Cenni preliminari sulle animazioni](animation-overview.md), [Cenni preliminari sugli storybard](storyboards-overview.md) e [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per animare un oggetto in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], creare una sequenza temporale, definire un'animazione (che rappresenti una effettiva modifica del valore di alcune proprietà nel tempo) e specificare la proprietà alla quale applicare l'animazione. Poiché tutti gli oggetti in una <xref:System.Windows.Controls.Viewport3D>scena 3D sono elementi figlio di , le proprietà di destinazione di qualsiasi animazione che si desidera applicare alla scena sono proprietà delle proprietà di Viewport3D.  
  
 Si supponga di voler creare un modello in grado di oscillare sul posto. È possibile scegliere <xref:System.Windows.Media.Media3D.RotateTransform3D> di applicare a al modello e animare l'asse della rotazione da un vettore a un altro. L'esempio di codice seguente illustra l'applicazione di un oggetto Vector3DAnimation alla proprietà Axis dell'oggetto Rotation3D della trasformazione, presupponendo che RotateTransform3D sia una delle diverse trasformazioni applicate al modello con un oggetto TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3-d-content-to-the-window"></a>Aggiungere contenuto tridimensionale alla finestra  
 Per eseguire il rendering della scena, aggiungere modelli e luci a un <xref:System.Windows.Media.Media3D.Model3DGroup>oggetto , quindi impostare il <xref:System.Windows.Media.Media3D.Model3DGroup> come di <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> un <xref:System.Windows.Media.Media3D.ModelVisual3D>. Aggiungere <xref:System.Windows.Media.Media3D.ModelVisual3D> l'oggetto all'insieme <xref:System.Windows.Controls.Viewport3D.Children%2A> del file <xref:System.Windows.Controls.Viewport3D>. Aggiungere telecamere <xref:System.Windows.Controls.Viewport3D> al impostando <xref:System.Windows.Controls.Viewport3D.Camera%2A> la sua proprietà.  
  
 Infine, aggiungere <xref:System.Windows.Controls.Viewport3D> il alla finestra. Quando <xref:System.Windows.Controls.Viewport3D> l'oggetto viene incluso come contenuto di un elemento di layout come <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> Canvas, specificate <xref:System.Windows.FrameworkElement>le dimensioni del Viewport3D impostandone le proprietà e (ereditate da ).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Cenni preliminari sulle trasformazioni tridimensionali](3-d-transformations-overview.md)
- [Ottimizzazione delle prestazioni tridimensionali di WPF](maximize-wpf-3d-performance.md)
- [Argomenti relativi alle procedure](3-d-graphics-how-to-topics.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
