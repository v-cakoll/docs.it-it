---
title: Panoramica della grafica 3D
description: Acquisire familiarità con la grafica 3D in Windows Presentation Foundation (WPF) per creare, trasformare e animare grafica 3D nel codice di markup e procedurale.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 51da6a1ed6d5e98b99c64ee23be52f7b2385897f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853881"
---
# <a name="3d-graphics-overview"></a>Panoramica della grafica 3D
<a name="introduction"></a>La funzionalità 3D in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consente agli sviluppatori di creare, trasformare e animare grafica 3D nel codice di markup e procedurale. Gli sviluppatori possono combinare grafica 2D e 3D per creare controlli avanzati, fornire illustrazioni complesse dei dati o migliorare l'esperienza utente dell'interfaccia di un'applicazione. il supporto 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non è progettato per offrire una piattaforma di sviluppo di giochi con funzionalità complete. Questo argomento fornisce una panoramica delle funzionalità 3D del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema grafico.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>3D in un contenitore 2D  
 il contenuto grafico 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è incapsulato in un elemento, <xref:System.Windows.Controls.Viewport3D> , che può partecipare alla struttura degli elementi bidimensionali. Il sistema grafico considera <xref:System.Windows.Controls.Viewport3D> come un elemento visivo bidimensionale come molti altri in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . <xref:System.Windows.Controls.Viewport3D>funziona come una finestra, ovvero un riquadro di visualizzazione, in una scena tridimensionale. Più precisamente, si tratta di una superficie sulla quale viene proiettata una scena 3D.  
  
 In un'applicazione 2D convenzionale usare <xref:System.Windows.Controls.Viewport3D> come un altro elemento contenitore come Grid o Canvas.  Sebbene sia possibile usare <xref:System.Windows.Controls.Viewport3D> con altri oggetti Drawing 2D nello stesso grafico della scena, non è possibile interpenetrare oggetti 2D e 3D in un oggetto <xref:System.Windows.Controls.Viewport3D> .  Questo argomento è incentrato su come creare grafica 3D all'interno di <xref:System.Windows.Controls.Viewport3D> .  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>Spazio delle coordinate 3D  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di coordinate per la grafica 2D individua l'origine nella parte superiore sinistra dell'area di rendering, in genere lo schermo. Nel sistema 2D, i valori positivi dell'asse x procedono verso destra e i valori positivi dell'asse y procedono verso il basso.  Nel sistema di coordinate 3D, tuttavia, l'origine si trova al centro dell'area di rendering, con i valori positivi dell'asse x che procedono verso destra, ma i valori positivi dell'asse y che procedono verso l'alto e i valori positivi dell'asse z che procedono verso l'esterno dall'origine verso il visualizzatore.  
  
 ![Sistemi di coordinate](./media/coordsystem-1.png "CoordSystem-1")  
Rappresentazioni convenzionali del sistema di coordinate 2D e 3D  
  
 Lo spazio definito da questi assi è il frame di riferimento fisso per gli oggetti 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Quando si compilano modelli in questo spazio e si creano luci e fotocamere per visualizzarli, è consigliabile distinguere il fotogramma di riferimento fisso, o "spazio globale", da quello di riferimento locale creato per ogni modello quando si applicano trasformazioni. Si ricordi anche che gli oggetti dello spazio globale possono avere un aspetto completamente diverso o non essere completamente visibili, a seconda delle impostazioni di luce e fotocamera e che la posizione della fotocamera tuttavia non modifica la posizione degli oggetti nello spazio globale.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Fotocamere e proiezioni  
 Gli sviluppatori che lavorano in 2D sono abituati a posizionare le primitive di disegno su una schermata bidimensionale. Quando si crea una scena 3D, è importante ricordare che si sta creando effettivamente una rappresentazione 2D degli oggetti 3D. Poiché una scena 3D ha un aspetto diverso a seconda del punto di vista dell'osservatore, è necessario specificare tale punto di visualizzazione. La <xref:System.Windows.Media.Media3D.Camera> classe consente di specificare questo punto di visualizzazione per una scena 3D.  
  
 Un altro modo per comprendere come una scena 3D viene rappresentata in una superficie 2D è la descrizione della scena come proiezione sulla superficie di visualizzazione. <xref:System.Windows.Media.Media3D.ProjectionCamera>Consente di specificare proiezioni diverse e le relative proprietà per modificare il modo in cui gli spettatori vedono i modelli 3D. Un oggetto <xref:System.Windows.Media.Media3D.PerspectiveCamera> specifica una proiezione che rappresenta uno scorcio la scena.  In altre parole, <xref:System.Windows.Media.Media3D.PerspectiveCamera> fornisce la prospettiva del punto di fuga.  È possibile specificare la posizione della fotocamera nello spazio delle coordinate della scena, la direzione e il campo visivo per la fotocamera, nonché un vettore che definisce la direzione verso l'alto nella scena. Il diagramma seguente illustra la <xref:System.Windows.Media.Media3D.PerspectiveCamera> proiezione di.  
  
 Le <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> proprietà e di <xref:System.Windows.Media.Media3D.ProjectionCamera> limitano l'intervallo della proiezione della fotocamera. Poiché le fotocamere possono trovarsi in qualsiasi punto della scena, è possibile che la fotocamera venga posizionata all'interno di un modello o accanto al modello stesso, rendendo difficile distinguere in modo corretto gli oggetti.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>consente di specificare una distanza minima dalla fotocamera oltre la quale non verranno disegnati gli oggetti.  Viceversa, consente di <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> specificare una distanza dalla fotocamera oltre la quale gli oggetti non verranno disegnati, garantendo che gli oggetti troppo lontani per essere riconoscibili non verranno inclusi nella scena.  
  
 ![Impostazione della fotocamera](./media/coordsystem-6.png "CoordSystem-6")  
Posizione della fotocamera  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>Specifica una proiezione ortogonale di un modello 3D in una superficie visiva 2D. In modo analogo ad altre fotocamere, l'oggetto specifica una posizione, una direzione di visualizzazione e una direzione verso l'alto. Diversamente da <xref:System.Windows.Media.Media3D.PerspectiveCamera> , tuttavia, <xref:System.Windows.Media.Media3D.OrthographicCamera> descrive una proiezione che non include lo scorcio prospettico. In altre parole, <xref:System.Windows.Media.Media3D.OrthographicCamera> descrive una casella di visualizzazione i cui lati sono paralleli, anziché uno i cui lati si trovano in un punto della fotocamera. Nella figura seguente viene illustrato lo stesso modello visualizzato utilizzando <xref:System.Windows.Media.Media3D.PerspectiveCamera> e <xref:System.Windows.Media.Media3D.OrthographicCamera> .  
  
 ![Proiezione ortografica e prospettica](./media/camera-projections4.png "Camera_projections4")  
Proiezioni prospettiche e ortografiche  
  
 Il codice seguente illustra alcune impostazioni tipiche della fotocamera.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Modello e primitive mesh  
  
 <xref:System.Windows.Media.Media3D.Model3D>è la classe di base astratta che rappresenta un oggetto 3D generico. Per creare una scena 3D, è necessario disporre di alcuni oggetti da visualizzare e gli oggetti che compongono il grafico della scena derivano da <xref:System.Windows.Media.Media3D.Model3D> . Attualmente supporta le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geometrie di modellazione con <xref:System.Windows.Media.Media3D.GeometryModel3D> . La <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di questo modello accetta una primitiva mesh.  
  
 Per compilare un modello, iniziare a compilare una primitiva (o mesh). Una primitiva 3D è una raccolta di vertici che formano una singola entità 3D. La maggior parte dei sistemi 3D fornisce primitive modellate nella figura chiusa più semplice: un triangolo definito da tre vertici.  Poiché i tre punti di un triangolo sono complanari, è possibile continuare ad aggiungere triangoli per modellare forme più complesse, denominate mesh.  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema 3D fornisce attualmente la <xref:System.Windows.Media.Media3D.MeshGeometry3D> classe, che consente di specificare qualsiasi geometria, ma attualmente non supporta primitive tridimensionali, ad esempio sfere e forme cubiche. Iniziare a creare un oggetto <xref:System.Windows.Media.Media3D.MeshGeometry3D> specificando un elenco di vertici del triangolo come <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Proprietà. Ogni vertice viene specificato come <xref:System.Windows.Media.Media3D.Point3D> .  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] specificare questa proprietà come un elenco di numeri raggruppati in tre che rappresentano le coordinate di ogni vertice. A seconda della geometria, è possibile che la mesh sia costituita da molti triangoli, alcuni dei quali condividono gli stessi angoli (vertici). Per disegnare la mesh in modo corretto, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono necessarie informazioni sui vertici condivisi e sui triangoli che li condividono. Queste informazioni vengono fornite specificando un elenco di indici di triangolo con la <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Proprietà. Questo elenco specifica l'ordine in cui i punti specificati nell' <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco determineranno un triangolo.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Nell'esempio precedente, l' <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco specifica otto vertici per definire una mesh a forma di cubo. La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> proprietà specifica un elenco di dodici gruppi di tre indici.  Ogni numero nell'elenco fa riferimento a un offset nell' <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco.  Ad esempio, i primi tre vertici specificati dall' <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco sono (1, 1, 0), (0, 1, 0) e (0, 0, 0). I primi tre indici specificati dall' <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> elenco sono 0, 2 e 1, che corrispondono al primo, terzo e secondo punto dell' <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> elenco. Il primo triangolo che costituisce il modello di cubo sarà pertanto composto da (1,1,0) a (0,1,0) a (0,0,0) e gli undici triangoli rimanenti vengono determinati in modo analogo.  
  
 È possibile continuare a definire il modello specificando i valori per le <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> proprietà e.  Per eseguire il rendering della superficie del modello, è necessario che il sistema grafico disponga delle informazioni per stabilire la direzione verso cui è rivolta la superficie in corrispondenza di tutti i triangoli specificati. Tali informazioni consentono al sistema di eseguire calcoli di illuminazione per il modello, con le superfici rivolte direttamente verso una sorgente di luce più brillanti rispetto a quelle con angolazione rispetto alla luce. Sebbene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sia in grado di determinare i vettori normali predefiniti usando le coordinate di posizione, è anche possibile specificare vettori normali diversi per avvicinarsi all'aspetto delle superfici curve.  
  
 La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> proprietà specifica una raccolta di <xref:System.Windows.Point> che indica al sistema grafico come eseguire il mapping delle coordinate che determinano la modalità di disegno di una trama nei vertici della mesh. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>vengono specificati come valore compreso tra zero e 1 inclusi.  Come per la <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> proprietà, il sistema grafico è in grado di calcolare le coordinate di trama predefinite, ma è possibile scegliere di impostare coordinate di trama diverse per controllare il mapping di una trama che include parte di un modello ripetuto, ad esempio. Per altre informazioni sulle coordinate di trama, vedere gli argomenti successivi oppure Managed Direct3D SDK.  
  
 L'esempio seguente illustra come creare una faccia del modello di cubo in codice procedurale. È possibile creare l'intero cubo come singolo GeometryModel3D. Questo esempio disegna la superficie del cubo come un modello distinto per applicare trame separate a ogni volto in un secondo momento.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>Applicazione di classi Material al modello  
  
 Affinché assuma l'aspetto di oggetto tridimensionale, è necessario che a una mesh venga applicata una trama per coprire la superficie definita dai relativi vertici e triangoli, in modo che possa essere illuminata e proiettata dalla fotocamera. In 2D si usa la <xref:System.Windows.Media.Brush> classe per applicare colori, modelli, sfumature o altro contenuto visivo alle aree dello schermo.  L'aspetto degli oggetti 3D, tuttavia, è una funzione del modello di illuminazione, non solo del colore o del modello applicato. Gli oggetti reali riflettono la luce in modo diverso in base alla qualità delle superfici. Le superfici lucide e brillanti non presentano infatti lo stesso aspetto delle superfici grezze o opache e alcuni oggetti sembrano assorbire la luce, mentre altri la riflettono. È possibile applicare tutti gli stessi pennelli agli oggetti 3D che è possibile applicare agli oggetti 2D, ma non è possibile applicarli direttamente.  
  
 Per definire le caratteristiche della superficie di un modello, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza la <xref:System.Windows.Media.Media3D.Material> classe astratta. Le sottoclassi concrete della classe Material determinano alcune caratteristiche di aspetto della superficie del modello e a ognuna è associata anche una proprietà Brush a cui è possibile passare un oggetto SolidColorBrush, TileBrush o VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>Specifica che il pennello verrà applicato al modello come se il modello fosse illuminato in modo diffuso. L'uso di DiffuseMaterial è molto simile all'uso dei pennelli direttamente nei modelli 2D; le superfici del modello non riflettono la luce come se fossero lucide.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>Specifica che il pennello verrà applicato al modello come se la superficie del modello fosse rigida o lucida, in grado di riflettere le evidenziazioni. È possibile impostare il livello in base al quale la trama suggerirà questa qualità riflettente o "Shine" specificando un valore per la <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> Proprietà.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>consente di specificare che la trama verrà applicata come se il modello emettesse una luce uguale al colore del pennello. In questo modo il modello non viene trasformato in luce ma partecipa in modo diverso all'applicazione di ombreggiatura rispetto a quanto accade nel caso di trama applicata con DiffuseMaterial o SpecularMaterial.  
  
 Per ottenere prestazioni migliori, i backface di un oggetto <xref:System.Windows.Media.Media3D.GeometryModel3D> (i visi che non sono in vista perché si trovano sul lato opposto del modello dalla fotocamera) vengono ritagliati dalla scena.  Per specificare un oggetto <xref:System.Windows.Media.Media3D.Material> da applicare alla parte posteriore di un modello, ad esempio un piano, impostare la <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà del modello.  
  
 Per ottenere alcune qualità della superficie, ad esempio l'effetto alone o riflettente, è necessario applicare a un modello più pennelli diversi in successione. È possibile applicare e riutilizzare più materiali utilizzando la <xref:System.Windows.Media.Media3D.MaterialGroup> classe. Gli elementi figlio di MaterialGroup vengono applicati dal primo all'ultimo in più passaggi di rendering.  
  
 Negli esempi di codice seguenti viene illustrato come applicare un colore a tinta unita e un disegno come pennelli ai modelli 3D.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Illuminazione della scena  
 Le luci nella grafica 3D consentono di eseguire le luci nel mondo reale, che rendono visibili le superfici. Più precisamente, le luci determinano la parte di scena che viene inclusa nella proiezione. Gli oggetti luce in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creano una varietà di luci e di effetti di ombreggiatura e sono modellati in base al comportamento di varie luci reali. Includere almeno una luce nella scena o nessun modello sarà visibile.  
  
 Le spie seguenti derivano dalla classe di base <xref:System.Windows.Media.Media3D.Light> :  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Fornisce illuminazione ambientale che illumina tutti gli oggetti in modo uniforme, indipendentemente dalla posizione o dall'orientamento.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Illumina come una sorgente di luce distante.  Le luci direzionali hanno un <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> specificato come Vector3D, ma non è specificato alcun percorso.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Illumina come una sorgente di luce vicina. Agli oggetti PointLights è associata una posizione dalla quale proiettano la luce. Gli oggetti nella scena vengono illuminati in base alla posizione e alla distanza rispetto alla luce. <xref:System.Windows.Media.Media3D.PointLightBase>espone una <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> proprietà che determina una distanza oltre la quale i modelli non verranno illuminati dalla luce. PointLight espone anche le proprietà di attenuazione, che determinano il modo in cui l'intensità della luce diminuisce rispetto alla distanza. Per l'attenuazione della luce, è possibile specificare interpolazioni costanti, lineari o quadratiche.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Eredita da <xref:System.Windows.Media.Media3D.PointLight> . Gli oggetti Spotlight illuminano come gli oggetti PointLight, dispongono di posizione e direzione Proiettano la luce in un'area a forma di cono impostata dalle <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> proprietà e, specificate in gradi.  
  
 Le luci sono <xref:System.Windows.Media.Media3D.Model3D> oggetti, quindi è possibile trasformare e animare proprietà chiare, tra cui posizione, colore, direzione e intervallo.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Trasformazione di modelli  
 Quando vengono creati, i modelli hanno una determinata posizione nella scena. Per spostare i modelli nella scena, ruotarli o modificarne la dimensione, non è pratico modificare i vertici che li definiscono,  Invece, così come in 2D, si applicano le trasformazioni ai modelli.  
  
 Ogni oggetto modello dispone di una <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà con la quale è possibile spostare, riorientare o ridimensionare il modello.  Quando si applica una trasformazione, si esegue in effetti l'offset di tutti i punti del modello in base a qualsiasi vettore o valore specificato dalla trasformazione. In altre parole, viene trasformato lo spazio delle coordinate in cui il modello è definito ("spazio modello"), ma non vengono modificati i valori che costituiscono la geometria del modello nel sistema di coordinate dell'intera scena ("spazio globale").  
  
 Per ulteriori informazioni sulla trasformazione dei modelli, vedere [Cenni preliminari sulle trasformazioni 3D](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Animazione di modelli  
 L' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementazione 3D fa parte dello stesso sistema di temporizzazione e animazione della grafica 2D. In altre parole, per animare una scena 3D, animare le proprietà dei relativi modelli. Anche se è possibile animare direttamente proprietà di primitive, in genere è più semplice animare trasformazioni che modificano la posizione o l'aspetto di modelli. Poiché le trasformazioni possono essere applicate a oggetti e a <xref:System.Windows.Media.Media3D.Model3DGroup> singoli modelli, è possibile applicare un set di animazioni a un figlio di un Model3DGroup e un altro set di animazioni a un gruppo di oggetti figlio. È possibile anche realizzare numerosi effetti visivi animando le proprietà di illuminazione della scena. È infine possibile scegliere di animare la proiezione stessa animando la posizione della fotocamera o il campo visivo. Per informazioni di base sul sistema di animazione e di temporizzazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere gli argomenti [Cenni preliminari sulle animazioni](animation-overview.md), [Cenni preliminari sugli storybard](storyboards-overview.md) e [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per animare un oggetto in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], creare una sequenza temporale, definire un'animazione (che rappresenti una effettiva modifica del valore di alcune proprietà nel tempo) e specificare la proprietà alla quale applicare l'animazione. Poiché tutti gli oggetti in una scena 3D sono elementi figlio di <xref:System.Windows.Controls.Viewport3D> , le proprietà di destinazione di qualsiasi animazione da applicare alla scena sono proprietà di Viewport3D.  
  
 Si supponga di voler creare un modello in grado di oscillare sul posto. È possibile scegliere di applicare un oggetto <xref:System.Windows.Media.Media3D.RotateTransform3D> al modello e animare l'asse della rotazione da un vettore a un altro. L'esempio di codice seguente illustra l'applicazione di un oggetto Vector3DAnimation alla proprietà Axis dell'oggetto Rotation3D della trasformazione, presupponendo che RotateTransform3D sia una delle diverse trasformazioni applicate al modello con un oggetto TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>Aggiungi contenuto 3D alla finestra  
 Per eseguire il rendering della scena, aggiungere modelli e luci a un oggetto <xref:System.Windows.Media.Media3D.Model3DGroup> , quindi impostare <xref:System.Windows.Media.Media3D.Model3DGroup> come <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> di un oggetto <xref:System.Windows.Media.Media3D.ModelVisual3D> . Aggiungere l'oggetto <xref:System.Windows.Media.Media3D.ModelVisual3D> alla <xref:System.Windows.Controls.Viewport3D.Children%2A> raccolta dell'oggetto <xref:System.Windows.Controls.Viewport3D> . Aggiungere fotocamere a <xref:System.Windows.Controls.Viewport3D> impostando la <xref:System.Windows.Controls.Viewport3D.Camera%2A> Proprietà.  
  
 Aggiungere infine alla <xref:System.Windows.Controls.Viewport3D> finestra di. Quando <xref:System.Windows.Controls.Viewport3D> è incluso come contenuto di un elemento di layout come Canvas, specificare le dimensioni dell'oggetto Viewport3D impostando le relative <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> proprietà e (ereditate da <xref:System.Windows.FrameworkElement> ).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Panoramica delle trasformazioni 3D](3-d-transformations-overview.md)
- [Ottimizzazione delle prestazioni tridimensionali di WPF](maximize-wpf-3d-performance.md)
- [Procedure](3-d-graphics-how-to-topics.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
