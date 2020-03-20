---
title: Sintassi di markup del percorso
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181854"
---
# <a name="path-markup-syntax"></a>Sintassi di markup del percorso
I percorsi sono illustrati in [Cenni preliminari](shapes-and-basic-drawing-in-wpf-overview.md) su Shapes e Basic Drawing in WPF e in [Panoramica della geometria](geometry-overview.md), [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]tuttavia in questo argomento vengono descritti in dettaglio il minilinguaggio potente e complesso che è possibile utilizzare per specificare le geometrie del percorso in modo più compatto utilizzando .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è necessario avere <xref:System.Windows.Media.Geometry> familiarità con le funzionalità di base degli oggetti. Per ulteriori informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Mini linguaggi StreamGeometry e PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce due classi che forniscono minilinguaggi <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>per la descrizione di percorsi geometrici: e .  
  
- Utilizzare il <xref:System.Windows.Media.StreamGeometry> minilinguaggio quando si <xref:System.Windows.Media.Geometry>imposta una <xref:System.Windows.UIElement.Clip%2A> proprietà di <xref:System.Windows.UIElement> tipo <xref:System.Windows.Shapes.Path.Data%2A> , <xref:System.Windows.Shapes.Path> ad esempio la proprietà di un o la proprietà di un elemento. Nell'esempio riportato di <xref:System.Windows.Media.StreamGeometry>seguito viene utilizzata la sintassi degli attributi per creare un oggetto .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- Utilizzare la <xref:System.Windows.Media.PathFigureCollection> minilingua quando <xref:System.Windows.Media.PathGeometry.Figures%2A> si imposta <xref:System.Windows.Media.PathGeometry>la proprietà di un oggetto . Nell'esempio riportato di seguito <xref:System.Windows.Media.PathFigureCollection> viene <xref:System.Windows.Media.PathGeometry>utilizzata una sintassi degli attributi per creare un oggetto per un oggetto .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Come si può notare dagli esempi precedenti, i due mini-linguaggi sono molto simili. E 'sempre possibile utilizzare <xref:System.Windows.Media.PathGeometry> un in qualsiasi situazione <xref:System.Windows.Media.StreamGeometry>in cui è possibile utilizzare un ; quindi quale dovresti usare? Utilizzare <xref:System.Windows.Media.StreamGeometry> un quando non è necessario modificare il percorso dopo averlo creato; utilizzare <xref:System.Windows.Media.PathGeometry> un se è necessario modificare il percorso.  
  
 Per ulteriori informazioni sulle <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> differenze tra e gli oggetti, vedere Cenni preliminari sulla [geometria](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Nota sugli spazi vuoti  
 Per brevità nelle sezioni di sintassi seguenti viene illustrato uno spazio singolo, ma sono accettabili più spazi quando viene visualizzato uno spazio singolo.  
  
 Due numeri in realtà non devono essere separati da una virgola o uno spazio vuoto, ma questo può essere fatto solo quando la stringa risultante non è ambigua. Ad esempio, `2..3` è in realtà due numeri: "2". e ".3". Allo stesso `2-3` modo, è "2" e "-3". Gli spazi non sono necessari né prima né dopo i comandi.  
  
### <a name="syntax"></a>Sintassi  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi di <xref:System.Windows.Media.StreamGeometry> utilizzo degli <xref:System.Windows.Media.FillRule> attributi per un oggetto è composta da un valore facoltativo e da una o più descrizioni di figure.  
  
|Utilizzo degli attributi XAML StreamGeometry|  
|-----------------------------------------|  
|`<``="` *proprietà* *dell'oggetto* [ `fillRule`] `figureDescription`[ ] `figureDescription``" ... />`|  
  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi di <xref:System.Windows.Media.PathFigureCollection> utilizzo degli attributi per un oggetto è composta da una o più descrizioni di figure.  
  
|Utilizzo degli attributi XAML PathFigureCollection|  
|-----------------------------------------------|  
|`<``figureDescription` `figureDescription` *proprietà* *object* `="` dell'oggetto [ ]`" ... />`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Specifica se <xref:System.Windows.Media.StreamGeometry> l'oggetto <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>utilizza l'oggetto <xref:System.Windows.Media.FillRule.EvenOdd> o .<br /><br /> -   `F0`specifica la <xref:System.Windows.Media.FillRule.EvenOdd> regola di riempimento.<br />-   `F1`specifica la <xref:System.Windows.Media.FillRule.Nonzero> regola di riempimento.<br /><br /> Se si osservere questo comando, il sottopercorso <xref:System.Windows.Media.FillRule.EvenOdd>utilizza il comportamento predefinito, ovvero . Se si specifica questo comando, è necessario inserirlo per primo.|  
|*figureDescription*|Figura costituita da un comando di spostamento, da alcuni comandi di disegno e da un comando di chiusura facoltativo.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Comando di spostamento che specifica il punto iniziale della figura. Vedere la sezione [Sposta comando.](#themovecommand)|  
|*drawCommands*|Uno o più comandi di disegno che descrivono il contenuto della figura. Vedere la sezione [Comandi di disegno.](#drawcommands)|  
|*closeCommand*|Comando facoltativo di chiusura che consente di chiudere la figura. Vedere la sezione [Chiudi comando.](#closecommand)|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Comando Move  
 Specifica il punto iniziale di una nuova figura.  
  
|Sintassi|  
|------------|  
|`M`*startPoint (Puntodi inizio)*<br /><br /> - oppure -<br /><br /> `m`*startPoint (Puntodi inizio)*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto iniziale di una nuova figura.|  
  
 Una maiuscola `M` indica `startPoint` che è un valore assoluto; una minuscola `m` indica `startPoint` che è un offset al punto precedente o (0,0) se non ne esiste nessuno. Se dopo il comando di spostamento vengono elencati più punti, verrà tracciata una linea in direzione di quei punti, anche se il comando della linea è stato specificato.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Comandi Draw  
 Un comando di disegno può essere costituito da diversi comandi di forma. Sono disponibili i comandi di forma seguenti: linea, linea orizzontale, linea verticale, curva di Bézier cubica, curva di Bézier quadratica, curva di Bézier cubica continua, curva di Bézier quadratica continua e arco ellittico.  
  
 Per inserire ciascun comando, usare una lettera maiuscola o una lettera minuscola: le lettere maiuscole indicano valori assoluti, quelle minuscole valori relativi. I punti di controllo del segmento specificato si riferiscono al punto finale dell'esempio precedente. Quando si immette in sequenza più comandi dello stesso tipo, è possibile omettere la voce di comando duplicata; ad esempio, `L 100,200 300,400` equivale `L 100,200 L 300,400`a . Nella tabella seguente vengono descritti i comandi **di spostamento** e **disegno.**  
  
### <a name="line-command"></a>Comando Line  
 Crea una linea retta tra il punto corrente e il punto finale specificato. `l 20 30`e `L 20,30` sono esempi di comandi **di linea** validi.  
  
|Sintassi|  
|------------|  
|`L`*endPoint (punto finale)*<br /><br /> - oppure -<br /><br /> `l`*endPoint (punto finale)*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*Endpoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto finale della linea.|  

Una maiuscola `L` indica `endPoint` che è un valore assoluto; una minuscola `l` indica `endPoint` che è un offset al punto precedente o (0,0) se non ne esiste nessuno.

### <a name="horizontal-line-command"></a>Comando Horizontal Line  
 Crea una linea orizzontale tra il punto corrente e la coordinata x specificata. `H 90` è un esempio di comando di linea orizzontale valido.

|Sintassi|  
|------------|  
|`H`  *X*<br /><br /> - oppure -<br /><br /> `h`  *X*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*X*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata x del punto finale della linea.|  
  
Una maiuscola `H` indica `x` che è un valore assoluto; una minuscola `h` indica `x` che è un offset al punto precedente o (0,0) se non ne esiste nessuno.
  
### <a name="vertical-line-command"></a>Comando Vertical Line  
 Crea una linea verticale tra il punto corrente e la coordinata y specificata. `v 90` è un esempio di comando di linea verticale valido.

|Sintassi|  
|------------|  
|`V`  *Y*<br /><br /> - oppure -<br /><br /> `v`  *Y*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*Y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata y del punto finale della linea.|  

Una maiuscola `V` indica `y` che è un valore assoluto; una minuscola `v` indica `y` che è un offset al punto precedente o (0,0) se non ne esiste nessuno.  

### <a name="cubic-bezier-curve-command"></a>Comando Cubic Bezier Curve  
 Crea una curva di Bézier cubica tra il punto corrente e`controlPoint`il `controlPoint`punto finale specificato utilizzando i due punti di controllo specificati ( 1 e 2). `C 100,200 200,400 300,200` è un esempio di comando di curva valido.  
  
|Sintassi|  
|------------|  
|`C``controlPoint`1`controlPoint`2 (in questo modo)`endPoint`<br /><br /> - oppure -<br /><br /> `c``controlPoint`1`controlPoint`2 (in questo modo)`endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Primo punto di controllo della curva, che determina la tangente iniziale della curva.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Secondo punto di controllo della curva, che determina la tangente finale della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando Quadratic Bezier Curve  
 Crea una curva di Bézier quadratica tra il punto corrente e`controlPoint`il punto finale specificato utilizzando il punto di controllo specificato ( ). `q 100,200 300,200` è un esempio di comando di curva di Bézier quadratica valido.  
  
|Sintassi|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oppure -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto di controllo della curva, che determina le tangenti iniziale e finale della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Comando Smooth cubic Bezier curve  
 Crea una curva di Bézier cubica tra il punto corrente e il punto finale specificato. Il primo punto di controllo viene considerato come reflection del secondo punto di controllo del comando precedente relativo al punto corrente. Se in precedenza non è stato usato alcun comando o se il comando precedente non era un comando di curva di Bézier cubica o un comando di curva di Bézier cubica continua, il punto di controllo coinciderà con il punto corrente. Il secondo punto di controllo, il punto di controllo `controlPoint`per l'estremità della curva, è specificato da 2. Ad esempio, `S 100,200 200,300` è un comando valido della curva di Bézier cubica uniforme.  
  
|Sintassi|  
|------------|  
|`S``controlPoint`2 Il nome del sistema`endPoint`<br /><br /> - oppure -<br /><br /> `s``controlPoint`2 Il nome del sistema`endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto di controllo della curva, che determina la tangente finale della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Comando Smooth Quadratic Bezier Curve  
 Crea una curva di Bézier quadratica tra il punto corrente e il punto finale specificato. Il punto di controllo viene considerato come reflection del punto di controllo del comando precedente relativo al punto corrente. Se in precedenza non è stato usato alcun comando o se il comando precedente non era un comando di curva di Bézier quadratica o un comando di curva di Bézier quadratica continua, il punto di controllo coinciderà con il punto corrente.  
  
|Sintassi|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> - oppure -<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto di controllo della curva, che determina l'inizio e la tangente della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="elliptical-arc-command"></a>Comando Elliptical Arc  
 Crea un arco ellittico tra il punto corrente e il punto finale specificato.  
  
|Sintassi|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> - oppure -<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> Raggio x e raggio y dell'arco.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Rotazione dell'ellisse in gradi.|  
|`isLargeArcFlag`|Impostato su 1 se la misura dell'angolo dell'arco deve essere di 180 gradi o superiore. In caso contrario, impostato su 0.|  
|`sweepDirectionFlag`|Impostato su 1 se l'arco viene tracciato nella direzione di un angolo positivo. In caso contrario, impostato su 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso cui viene disegnata l'arco.|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a>Comando Close  
 Termina la figura corrente e crea una linea che collega il punto corrente e il punto iniziale della figura. Questo comando crea una giunzione di linee (angolo) tra l'ultimo segmento e il primo segmento della figura.  
  
|Sintassi|  
|------------|  
|`Z`<br /><br /> - oppure -<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>Sintassi del punto  
 Descrive le coordinate x e y di un punto in cui (0,0) è l'angolo superiore sinistro.
  
|Sintassi|  
|------------|  
|`x` `,` `y`<br /><br /> - oppure -<br /><br /> `x` `y`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata x del punto.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata y del punto.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Valori speciali  
 Anziché un valore numerico standard, è anche possibile usare i valori speciali seguenti. Per questi valori viene effettuata la distinzione tra maiuscole e minuscole.  
  
 Infinity  
 Rappresenta <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.  
  
 -Infinito  
 Rappresenta <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.  
  
 NaN  
 Rappresenta <xref:System.Double.NaN?displayProperty=nameWithType>.  
  
 È anche possibile usare una notazione scientifica. Ad esempio, `+1.e17` è un valore valido.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Argomenti relativi alle procedure](geometries-how-to-topics.md)
