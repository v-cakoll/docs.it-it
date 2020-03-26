---
title: Panoramica delle trasformazioni 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D transformations
- transformations [WPF], 3D
ms.assetid: e45e555d-ac1e-4b36-aced-e433afe7f27f
ms.openlocfilehash: 0efd6d247f23760c878c82cc92e99f1b83c1b9d2
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112349"
---
# <a name="3d-transformations-overview"></a>Panoramica delle trasformazioni 3D
In questo argomento viene descritto come applicare trasformazioni ai modelli 3D nel sistema [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] grafico. Le trasformazioni consentono allo sviluppatore di riposizionare, ridimensionare e orientare nuovamente i modelli senza modificare i valori di base che li definiscono.  

## <a name="3d-coordinate-space"></a>Spazio coordinate 3D  
 Il contenuto grafico [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D in è <xref:System.Windows.Controls.Viewport3D>incapsulato in un elemento, , che può partecipare alla struttura dell'elemento bidimensionale. Il sistema grafico considera Viewport3D come un oggetto visivo bidimensionale in modo analogo a molti altri in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viewport3D funziona come una finestra, ovvero un riquadro di visualizzazione, in una scena tridimensionale. Più precisamente, è una superficie su cui viene proiettata una scena 3D.  Sebbene sia possibile utilizzare Viewport3D con altri oggetti di disegno 2D nello stesso grafico di scena, non è possibile interpenetrare gli oggetti 2D e 3D all'interno di un Viewport3D. Nella discussione seguente lo spazio delle coordinate descritto è contenuto nell'elemento Viewport3D.  
  
 Il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema di coordinate per la grafica 2D individua l'origine nella parte superiore sinistra della superficie di rendering (in genere lo schermo). Nel sistema 2D, i valori positivi dell'asse x procedono a destra e i valori positivi dell'asse y procedono verso il basso. Nel sistema di coordinate 3D, tuttavia, l'origine si trova al centro dello schermo, con i valori positivi dell'asse x che procedono verso destra, ma i valori positivi dell'asse y procedono invece verso l'alto, e valori positivi dell'asse z che procedono verso l'esterno dall'origine, verso l'visualizzatore.  
  
 ![Sistemi di coordinate](./media/coordsystem-1.png "CoordSystem-1")  
Confronto tra sistemi di coordinate  
  
 Lo spazio definito da questi assi è il telaio di riferimento fisso per gli oggetti 3D in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Quando si compilano modelli in questo spazio e si creano luci e fotocamere per visualizzarli, è consigliabile distinguere il fotogramma di riferimento fisso, o "spazio globale", da quello di riferimento locale creato per ogni modello quando si applicano trasformazioni. Si ricordi anche che gli oggetti dello spazio globale possono avere un aspetto completamente diverso o non essere completamente visibili, a seconda delle impostazioni di luce e fotocamera e che la posizione della fotocamera tuttavia non modifica la posizione degli oggetti nello spazio globale.  
  
## <a name="transforming-models"></a>Trasformazione di modelli  
 Quando vengono creati, i modelli hanno una determinata posizione nella scena. Per spostare i modelli nella scena, ruotarli o modificarne la dimensione, non è pratico modificare i vertici che li definiscono, Invece, proprio come in 2D, si applicano trasformazioni ai modelli.  
  
 Ogni oggetto modello <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> dispone di una proprietà con cui è possibile spostare, riorientare o ridimensionare il modello. Quando si applica una trasformazione, si esegue in effetti l'offset di tutti i punti del modello in base a qualsiasi vettore o valore specificato dalla trasformazione. In altre parole, viene trasformato lo spazio delle coordinate in cui il modello è definito ("spazio modello"), ma non vengono modificati i valori che costituiscono la geometria del modello nel sistema di coordinate dell'intera scena ("spazio globale").  
  
## <a name="translation-transformations"></a>Trasformazioni di traslazione  
 Le trasformazioni 3D ereditano <xref:System.Windows.Media.Media3D.Transform3D>dalla classe base astratta ; queste includono le classi <xref:System.Windows.Media.Media3D.TranslateTransform3D> <xref:System.Windows.Media.Media3D.ScaleTransform3D>di <xref:System.Windows.Media.Media3D.RotateTransform3D>trasformazione affine , , e . Il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema 3D <xref:System.Windows.Media.Media3D.MatrixTransform3D> fornisce anche una classe che consente di specificare le stesse trasformazioni in operazioni di matrice più concise.  
  
 <xref:System.Windows.Media.Media3D.TranslateTransform3D>sposta tutti i punti nel Model3D nella direzione del <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetY%2A>vettore <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetZ%2A> di offset specificato con le proprietà , e . Dato un vertice di un cubo a (2,2,2), ad esempio, un vettore offset di (0,1.6,1) sposta tale vertice da (2,2,2) a (2,3.6,3). Il vertice del cubo è ancora (2,2,2) nello spazio modello ma, dal momento che è stata modificata la relazione tra tale spazio e lo spazio globale, risulta che (2,2,2) nello spazio modello diventa (2,3.6,3) nello spazio globale.  
  
 ![Figura di traslazione](./media/transforms-translate.png "Trasformazioni-Traduzione")  
Traslazione con offset  
  
 Gli esempi di codice seguente illustrano come applicare una traslazione.  
  
 [!code-xaml[animation3dgallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="scale-transformations"></a>Trasformazioni di scala  
 <xref:System.Windows.Media.Media3D.ScaleTransform3D>modifica la scala del modello di un vettore di scala specificato con riferimento a un punto centrale. Specificare una scala uniforme, che adatti il modello in base allo stesso valore sugli assi X, Y e Z, in modo da modificare la dimensione del modello proporzionalmente. Ad esempio, l'impostazione <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>delle <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> proprietà <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>, e della trasformazione su 0,5 dimezza le dimensioni del modello; l'impostazione delle stesse proprietà su 2 raddoppia la scala in tutti e tre gli assi.  
  
 ![ScaleTransform3D uniforme](./media/threecubes-uniformscale-1.png "threecubes_uniformscale_1")  
Esempio di ScaleVector  
  
 Se si specifica una trasformazione di scala non uniforme, ovvero una trasformazione in cui i valori X, Y e Z non sono tutti uguali, è possibile generare un modello da estendere o comprimere in una o due dimensioni senza influire sulle altre. Ad esempio, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> l'impostazione su 1, <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> su 2 e <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> su 1 causerebbe il raddoppio dell'altezza del modello trasformato, ma rimarrà invariato lungo gli assi X e .  
  
 Per impostazione predefinita, ScaleTransform3D determina l'espansione o la contrazione di vertici intorno all'origine (0,0,0). Se il modello da trasformare non è stato creato dall'origine, tuttavia, il ridimensionamento del modello dall'origine non si adatterà al modello sul posto. Quando i vertici del modello vengono moltiplicati per il vettore di ridimensionamento, l'operazione di ridimensionamento ha invece l'effetto di traslare il modello e di ridimensionarlo.  
  
 ![Tre cubi ridimensionati con punto centrale specificato](./media/threecubes-scaledwithcenter-1.png "threecubes_scaledwithcenter_1")  
Esempio di centro di ridimensionamento  
  
 Per ridimensionare un modello "sul posto", specificare il centro del <xref:System.Windows.Media.ScaleTransform.CenterX%2A>modello <xref:System.Windows.Media.ScaleTransform.CenterY%2A>impostando <xref:System.Windows.Media.Media3D.ScaleTransform3D.CenterZ%2A> le proprietà , e di ScaleTransform3D. Ciò garantisce che il sistema grafico ridimensiona lo spazio modello <xref:System.Windows.Media.Media3D.Point3D>e quindi lo converte in centro sul file specificato. Se invece il modello è stato creato intorno all'origine e si specifica un punto centrale diverso, il modello viene traslato lontano dall'origine.  
  
## <a name="rotation-transformations"></a>Trasformazioni di rotazione  
 È possibile ruotare un modello in 3D in diversi modi. Una trasformazione di rotazione tipica specifica un asse e un angolo di rotazione intorno a tale asse. La <xref:System.Windows.Media.Media3D.RotateTransform3D> classe consente di <xref:System.Windows.Media.Media3D.Rotation3D> definire <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> un con la relativa proprietà. È quindi <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> possibile specificare e le proprietà <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>su Rotation3D, in questo caso un , per definire la trasformazione. Gli esempi seguenti ruotano un modello di 60 gradi intorno all'asse Y.  
  
 [!code-xaml[animation3dgallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
 Nota:[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D è un sistema destrorso, il che significa che un valore di angolo positivo per una rotazione si traduce in una rotazione in senso antiorario intorno all'asse.  
  
 Le rotazioni asse-angolo presuppongono una rotazione intorno <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterX%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterY%2A>all'origine se non viene specificato un valore per le proprietà , e in <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterZ%2A> RotateTransform3D. Come per il ridimensionamento, è opportuno ricordare che la rotazione trasforma l'intero spazio delle coordinate del modello. Se il modello è stato creato intorno all'origine oppure è stato traslato in precedenza, la rotazione potrebbe girare rispetto all'origine invece di ruotare sul posto.  
  
 ![Rotazione con nuovo punto centrale](./media/threecubes-rotationwithcenter-1.png "threecubes_rotationwithcenter_1")  
Rotazione con nuovo centro specificato  
  
 Per ruotare il modello sul posto, specificare il centro effettivo del modello come centro di rotazione. Poiché la geometria si basa in genere sull'origine, molto spesso è possibile ottenere il risultato previsto di un set di trasformazioni adattando il modello (ridimensionandolo), quindi impostando l'orientamento (ruotandolo) e infine spostandolo nella posizione desiderata (traslandolo).  
  
 ![Rotazione di 60 gradi rispetto agli assi x&#45; e y&#45;](./media/twocubes-rotation2axes-1.png "twocubes_rotation2axes_1")  
Esempio di rotazione  
  
 Le rotazioni asse-angolo sono particolarmente utili per le trasformazioni statiche e per alcune animazioni. È consigliabile tuttavia ruotare il modello di un cubo di 60 gradi rispetto all'asse X, quindi di 45 gradi rispetto all'asse Z. È possibile descrivere questa trasformazione come due distinte trasformazioni analoghe o come una matrice. Potrebbe risultare difficile, tuttavia, animare correttamente una rotazione definita in questo modo. Sebbene le posizioni iniziale e finale del modello calcolate da uno dei due approcci siano le stesse, le posizioni intermedie assunte dal modello non sono definite dal punto di vista del calcolo. I quaternioni costituiscono un modo alternativo di calcolare l'interpolazione tra l'inizio e la fine di una rotazione.  
  
 Un quaternione rappresenta un asse nello spazio 3D e una rotazione intorno a tale asse. Un quaternione può rappresentare ad esempio un asse (1,1,2) e una rotazione di 50 gradi. La capacità dei quaternioni di definire le rotazioni deriva dalle due operazioni che è possibile eseguire su di essi, ovvero composizione e interpolazione. La composizione di due quaternioni applicata alla geometria significa "ruotare la geometria intorno all'asse 2 con la rotazione 2, quindi ruotarla intorno all'asse 1 con la rotazione 1". Grazie alla composizione, è possibile combinare le due rotazioni relative alla geometria per ottenere un singolo quaternione che costituisce il risultato. Poiché l'interpolazione dei quaternioni consente di calcolare un tracciato corretto e adeguato da un asse e da un orientamento all'altro, è possibile eseguire l'interpolazione dal quaternione originale a quello composto per ottenere una transizione corretta dall'uno all'altro, con la possibilità di animare la trasformazione. Per i modelli che si desidera animare, è possibile specificare una destinazione <xref:System.Windows.Media.Media3D.Quaternion> per la rotazione utilizzando un <xref:System.Windows.Media.Media3D.QuaternionRotation3D> per la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà .  
  
## <a name="using-transformation-collections"></a>Uso di raccolte di trasformazione  
 Quando si crea una scena, è normale applicare più di una trasformazione a un modello. Aggiungere trasformazioni <xref:System.Windows.Media.Media3D.Transform3DGroup.Children%2A> alla raccolta <xref:System.Windows.Media.Media3D.Transform3DGroup> della classe per raggruppare le trasformazioni in modo pratico da applicare avari modelli nella scena. È spesso consigliabile usare nuovamente una trasformazione in vari gruppi differenti, in modo molto simile a quanto avviene per il nuovo uso di un modello applicando un set diverso di trasformazioni a ogni istanza. Si noti che l'ordine in cui le trasformazioni vengono aggiunte alle raccolte è significativo. Le trasformazioni nella raccolta vengono infatti applicate dalla prima all'ultima.  
  
## <a name="animating-transformations"></a>Animazione delle trasformazioni  
 L'implementazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D partecipa allo stesso sistema di temporizzazione e animazione della grafica 2D. In altre parole, per animare una scena 3D, animare le proprietà dei relativi modelli. Anche se è possibile animare direttamente proprietà di primitive, in genere è più semplice animare trasformazioni che modificano la posizione o l'aspetto di modelli. Poiché le trasformazioni <xref:System.Windows.Media.Media3D.Model3DGroup> possono essere applicate agli oggetti e ai singoli modelli, è possibile applicare un set di animazioni agli elementi figlio di un Model3Dgroup e un altro set di animazioni a un gruppo di oggetti.  Per informazioni di base sul sistema di temporizzazione e di animazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere [Cenni preliminari sulle animazioni](animation-overview.md) e [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 Per animare un oggetto in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], creare una sequenza temporale, definire un'animazione (che rappresenti una effettiva modifica del valore di alcune proprietà nel tempo) e specificare la proprietà alla quale applicare l'animazione, che deve essere una proprietà di un oggetto FrameworkElement. Poiché tutti gli oggetti in una scena 3D sono elementi figlio di Viewport3D, le proprietà di destinazione di qualsiasi animazione che si desidera applicare alla scena sono proprietà delle proprietà di Viewport3D. È importante elaborare con attenzione il tracciato di proprietà per l'animazione, in quanto la sintassi può risultare ridondante.  
  
 Si supponga di voler ruotare un oggetto sul posto, ma anche di applicare un movimento oscillante per esporre un'area maggiore dell'oggetto da visualizzare. È possibile scegliere di applicare un oggetto RotateTransform3D e animare l'asse di rotazione da un vettore a un altro. Nell'esempio di codice <xref:System.Windows.Media.Animation.Vector3DAnimation> riportato di seguito viene illustrata l'applicazione di a una proprietà alla proprietà Axis dell'oggetto <xref:System.Windows.Media.TransformGroup>Rotation3D della trasformazione, presupponendo che RotateTransform3D sia una delle diverse trasformazioni applicate al modello con un oggetto .  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 Usare una sintassi analoga per gestire altre proprietà di trasformazione in modo da spostare o ridimensionare l'oggetto.  Ad esempio, è <xref:System.Windows.Media.Animation.Point3DAnimation> possibile applicare a alla proprietà ScaleCenter in una trasformazione di scala per fare in modo che un modello ne distorca uniformemente la forma.  
  
 Sebbene gli esempi precedenti <xref:System.Windows.Media.Media3D.GeometryModel3D>trasformino le proprietà di , è anche possibile trasformare le proprietà di altri modelli nella scena.  Se si animano le traslazioni applicate agli oggetti luce, è possibile ad esempio creare luci mobili ed effetti di ombreggiatura che possono cambiare sensibilmente l'aspetto grafico dei modelli.  
  
 Poiché anche le fotocamere sono modelli, è possibile trasformare anche le proprietà delle fotocamere.  Sebbene sia possibile modificare l'aspetto grafico della scena trasformando la posizione della fotocamera o le distanze del piano, trasformando di fatto l'intera proiezione della scena, si noti che molti effetti raggiungibili in questo modo non hanno molto senso visivo per il visualizzatore rispetto alle trasformazioni applicate al percorso o alla posizione dei modelli nella scena.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
