---
title: Sintassi di markup del percorso
description: Informazioni sul mini-linguaggio potente e complesso che è possibile usare per specificare geometrie di tracciato compatte in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 6d2778522b622f0b0dcb59673e793a6d772a4b4f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853655"
---
# <a name="path-markup-syntax"></a>Sintassi di markup del percorso
I percorsi sono descritti in [forme e disegno di base in Cenni preliminari su WPF](shapes-and-basic-drawing-in-wpf-overview.md) e [Cenni preliminari sulla geometria](geometry-overview.md). Tuttavia, in questo argomento viene descritto in dettaglio il mini linguaggio potente e complesso che è possibile usare per specificare geometrie di percorso in modo più compatto usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base degli <xref:System.Windows.Media.Geometry> oggetti. Per altre informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Mini linguaggi StreamGeometry e PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in sono disponibili due classi che forniscono mini-linguaggi per la descrizione dei percorsi geometrici: <xref:System.Windows.Media.StreamGeometry> e <xref:System.Windows.Media.PathFigureCollection> .  
  
- È possibile utilizzare il <xref:System.Windows.Media.StreamGeometry> linguaggio miniaturizzato quando si imposta una proprietà di tipo <xref:System.Windows.Media.Geometry> , ad esempio la <xref:System.Windows.UIElement.Clip%2A> proprietà di un oggetto <xref:System.Windows.UIElement> o la <xref:System.Windows.Shapes.Path.Data%2A> proprietà di un <xref:System.Windows.Shapes.Path> elemento. Nell'esempio seguente viene usata la sintassi dell'attributo per creare un oggetto <xref:System.Windows.Media.StreamGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- Usare il <xref:System.Windows.Media.PathFigureCollection> linguaggio miniaturizzato quando si imposta la <xref:System.Windows.Media.PathGeometry.Figures%2A> proprietà di un oggetto <xref:System.Windows.Media.PathGeometry> . Nell'esempio seguente viene utilizzata una sintassi di attributo per creare un oggetto <xref:System.Windows.Media.PathFigureCollection> per un oggetto <xref:System.Windows.Media.PathGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Come si può notare dagli esempi precedenti, i due mini-linguaggi sono molto simili. È sempre possibile usare un oggetto <xref:System.Windows.Media.PathGeometry> in qualsiasi situazione in cui è possibile usare un oggetto <xref:System.Windows.Media.StreamGeometry> , quindi quale è consigliabile usare? Utilizzare un oggetto <xref:System.Windows.Media.StreamGeometry> quando non è necessario modificare il percorso dopo la creazione. utilizzare un <xref:System.Windows.Media.PathGeometry> se è necessario modificare il percorso.  
  
 Per ulteriori informazioni sulle differenze tra <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> gli oggetti e, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Nota sugli spazi vuoti  
 Per brevità nelle sezioni di sintassi seguenti viene illustrato uno spazio singolo, ma sono accettabili più spazi quando viene visualizzato uno spazio singolo.  
  
 In realtà, due numeri non devono essere separati da una virgola o da uno spazio vuoto, ma questa operazione può essere eseguita solo quando la stringa risultante non è ambigua. Ad esempio, `2..3` è in realtà costituito da due numeri: "2". e ".3". Analogamente, `2-3` è "2" e "-3". Gli spazi non sono necessari né prima né dopo i comandi.  
  
### <a name="syntax"></a>Sintassi  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi di utilizzo degli attributi per un oggetto <xref:System.Windows.Media.StreamGeometry> è costituita da un <xref:System.Windows.Media.FillRule> valore facoltativo e da una o più descrizioni di figure.  
  
|Utilizzo degli attributi XAML StreamGeometry|  
|-----------------------------------------|  
|`<`*Object* *property* `="` (proprietà `fillRule` ) [] `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi di utilizzo degli attributi per un oggetto <xref:System.Windows.Media.PathFigureCollection> è costituita da una o più descrizioni di figure.  
  
|Utilizzo degli attributi XAML PathFigureCollection|  
|-----------------------------------------------|  
|`<`*Object* *property* `="` `figureDescription` (proprietà `figureDescription` ) [] *`" ... />`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Specifica se <xref:System.Windows.Media.StreamGeometry> Usa <xref:System.Windows.Media.FillRule.EvenOdd> o <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .<br /><br /> -   `F0`Specifica la <xref:System.Windows.Media.FillRule.EvenOdd> regola di riempimento.<br />-   `F1`Specifica la <xref:System.Windows.Media.FillRule.Nonzero> regola di riempimento.<br /><br /> Se si omette questo comando, il sottopercorso usa il comportamento predefinito, ovvero <xref:System.Windows.Media.FillRule.EvenOdd> . Se si specifica questo comando, è necessario inserirlo per primo.|  
|*figureDescription*|Figura costituita da un comando di spostamento, da alcuni comandi di disegno e da un comando di chiusura facoltativo.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Comando di spostamento che specifica il punto iniziale della figura. Vedere la sezione [comando Move](#themovecommand) .|  
|*drawCommands*|Uno o più comandi di disegno che descrivono il contenuto della figura. Vedere la sezione [comandi di estrazione](#drawcommands) .|  
|*closeCommand*|Comando facoltativo di chiusura che consente di chiudere la figura. Vedere la sezione [comando Chiudi](#closecommand) .|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Comando Move  
 Specifica il punto iniziale di una nuova figura.  
  
|Sintassi|  
|------------|  
|`M`punto *iniziale*<br /><br /> - oppure -<br /><br /> `m`punto *iniziale*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto iniziale di una nuova figura.|  
  
 Una lettera maiuscola `M` indica che `startPoint` è un valore assoluto. un valore minuscolo `m` indica che `startPoint` è un offset rispetto al punto precedente oppure (0,0) se non ne esiste alcuno. Se dopo il comando di spostamento vengono elencati più punti, verrà tracciata una linea in direzione di quei punti, anche se il comando della linea è stato specificato.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Comandi Draw  
 Un comando di disegno può essere costituito da diversi comandi di forma. Sono disponibili i comandi di forma seguenti: linea, linea orizzontale, linea verticale, curva di Bézier cubica, curva di Bézier quadratica, curva di Bézier cubica continua, curva di Bézier quadratica continua e arco ellittico.  
  
 Per inserire ciascun comando, usare una lettera maiuscola o una lettera minuscola: le lettere maiuscole indicano valori assoluti, quelle minuscole valori relativi. I punti di controllo del segmento specificato si riferiscono al punto finale dell'esempio precedente. Quando si immette in sequenza più di un comando dello stesso tipo, è possibile omettere la voce di comando duplicata; ad esempio, `L 100,200 300,400` è equivalente a `L 100,200 L 300,400` . Nella tabella seguente vengono descritti i comandi di **spostamento** e di **estrazione** .  
  
### <a name="line-command"></a>Comando Line  
 Crea una linea retta tra il punto corrente e il punto finale specificato. `l 20 30`e `L 20,30` sono esempi di comandi di **riga** validi.  
  
|Sintassi|  
|------------|  
|`L`*endpoint* di<br /><br /> - oppure -<br /><br /> `l`*endpoint* di|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*endPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto finale della linea.|  

Una lettera maiuscola `L` indica che `endPoint` è un valore assoluto. un valore minuscolo `l` indica che `endPoint` è un offset rispetto al punto precedente oppure (0,0) se non ne esiste alcuno.

### <a name="horizontal-line-command"></a>Comando Horizontal Line  
 Crea una linea orizzontale tra il punto corrente e la coordinata x specificata. `H 90` è un esempio di comando di linea orizzontale valido.

|Sintassi|  
|------------|  
|`H`  *x*<br /><br /> - oppure -<br /><br /> `h`  *x*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata x del punto finale della linea.|  
  
Una lettera maiuscola `H` indica che `x` è un valore assoluto. un valore minuscolo `h` indica che `x` è un offset rispetto al punto precedente oppure (0,0) se non ne esiste alcuno.
  
### <a name="vertical-line-command"></a>Comando Vertical Line  
 Crea una linea verticale tra il punto corrente e la coordinata y specificata. `v 90` è un esempio di comando di linea verticale valido.

|Sintassi|  
|------------|  
|`V`  *y*<br /><br /> - oppure -<br /><br /> `v`  *y*|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata y del punto finale della linea.|  

Una lettera maiuscola `V` indica che `y` è un valore assoluto. un valore minuscolo `v` indica che `y` è un offset rispetto al punto precedente oppure (0,0) se non ne esiste alcuno.  

### <a name="cubic-bezier-curve-command"></a>Comando Cubic Bezier Curve  
 Crea una curva di Bezier cubica tra il punto corrente e il punto finale specificato usando i due punti di controllo specificati ( `controlPoint` 1 e `controlPoint` 2). `C 100,200 200,400 300,200` è un esempio di comando di curva valido.  
  
|Sintassi|  
|------------|  
|`C``controlPoint`1 `controlPoint` 2`endPoint`<br /><br /> - oppure -<br /><br /> `c``controlPoint`1 `controlPoint` 2`endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Primo punto di controllo della curva, che determina la tangente iniziale della curva.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Secondo punto di controllo della curva, che determina la tangente finale della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando Quadratic Bezier Curve  
 Crea una curva di Bézier quadratica tra il punto corrente e il punto finale specificato usando il punto di controllo specificato ( `controlPoint` ). `q 100,200 300,200` è un esempio di comando di curva di Bézier quadratica valido.  
  
|Sintassi|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oppure -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto di controllo della curva, che determina le tangenti iniziale e finale della curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto verso il quale viene disegnata la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Comando Smooth cubic Bezier curve  
 Crea una curva di Bézier cubica tra il punto corrente e il punto finale specificato. Il primo punto di controllo viene considerato come reflection del secondo punto di controllo del comando precedente relativo al punto corrente. Se in precedenza non è stato usato alcun comando o se il comando precedente non era un comando di curva di Bézier cubica o un comando di curva di Bézier cubica continua, il punto di controllo coinciderà con il punto corrente. Il secondo punto di controllo, il punto di controllo per la fine della curva, viene specificato da `controlPoint` 2. Ad esempio, `S 100,200 200,300` è un comando di curva di Bezier cubica valido.  
  
|Sintassi|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> - oppure -<br /><br /> `s``controlPoint`2`endPoint`|  
  
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
 Descrive le coordinate x e y di un punto in cui (0, 0) è l'angolo superiore sinistro.
  
|Sintassi|  
|------------|  
|`x` `,` `y`<br /><br /> - oppure -<br /><br /> `x` `y`|  
  
|Termine|Descrizione|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata x del punto.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordinata y del punto.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Valori speciali  
 Anziché un valore numerico standard, è anche possibile usare i valori speciali seguenti. Per questi valori viene fatta distinzione tra maiuscole e minuscole.  
  
 Infinito  
 Rappresenta <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> .  
  
 -Infinito  
 Rappresenta <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> .  
  
 NaN  
 Rappresenta <xref:System.Double.NaN?displayProperty=nameWithType> .  
  
 È anche possibile usare una notazione scientifica. Ad esempio, `+1.e17` è un valore valido.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Procedure](geometries-how-to-topics.md)
