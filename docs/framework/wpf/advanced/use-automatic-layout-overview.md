---
title: Cenni preliminari sull'utilizzo del layout automatico
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 2fe473da3eeabef3852e3003e61b3b9604332855
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291266"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="a747c-102">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="a747c-102">Use Automatic Layout Overview</span></span>

<span data-ttu-id="a747c-103">In questo argomento vengono presentate le linee guida per gli sviluppatori su come scrivere applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con interfacce utente localizzabili (UI).</span><span class="sxs-lookup"><span data-stu-id="a747c-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable user interfaces (UIs).</span></span> <span data-ttu-id="a747c-104">In passato, la localizzazione di un'interfaccia utente era un processo che richiedeva molto tempo.</span><span class="sxs-lookup"><span data-stu-id="a747c-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="a747c-105">Ogni lingua in cui l'interfaccia utente è stata adattata per la regolazione del pixel è necessaria.</span><span class="sxs-lookup"><span data-stu-id="a747c-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="a747c-106">Oggi, con la progettazione corretta e gli standard di codifica corretti, le interfacce utente possono essere costruite in modo che i localizzatori abbiano un minor ridimensionamento e un riposizionamento.</span><span class="sxs-lookup"><span data-stu-id="a747c-106">Today with the right design and right coding standards, UIs can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="a747c-107">L'approccio alla scrittura di applicazioni che possono essere ridimensionate e riposizionate più facilmente viene definito layout automatico e può essere eseguito utilizzando la progettazione di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a747c-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="a747c-108">Vantaggi dell'uso del layout automatico</span><span class="sxs-lookup"><span data-stu-id="a747c-108">Advantages of Using Automatic Layout</span></span>

<span data-ttu-id="a747c-109">Poiché il sistema di presentazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è potente e flessibile, offre la possibilità di applicare il layout degli elementi di un'applicazione che possono essere modificati in base ai requisiti di lingue diverse.</span><span class="sxs-lookup"><span data-stu-id="a747c-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="a747c-110">L'elenco seguente indica alcuni vantaggi del layout automatico.</span><span class="sxs-lookup"><span data-stu-id="a747c-110">The following list points out some of the advantages of automatic layout.</span></span>

- <span data-ttu-id="a747c-111">L'interfaccia utente viene visualizzata correttamente in qualsiasi lingua.</span><span class="sxs-lookup"><span data-stu-id="a747c-111">UI displays well  in any language.</span></span>

- <span data-ttu-id="a747c-112">Riduce l'esigenza di ulteriori modifiche alla posizione e alle dimensioni dei controlli dopo la traduzione del testo.</span><span class="sxs-lookup"><span data-stu-id="a747c-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>

- <span data-ttu-id="a747c-113">Riduce l'esigenza di ulteriori modifiche alle dimensioni delle finestre.</span><span class="sxs-lookup"><span data-stu-id="a747c-113">Reduces the need to readjust window size.</span></span>

- <span data-ttu-id="a747c-114">Il layout dell'interfaccia utente viene visualizzato correttamente in qualsiasi lingua.</span><span class="sxs-lookup"><span data-stu-id="a747c-114">UI layout renders properly in any language.</span></span>

- <span data-ttu-id="a747c-115">La localizzazione può essere ridotta a semplici attività che vanno poco oltre la traduzione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="a747c-115">Localization can be reduced to the point that it is little more than string translation.</span></span>

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a><span data-ttu-id="a747c-116">Layout automatico e controlli</span><span class="sxs-lookup"><span data-stu-id="a747c-116">Automatic Layout and Controls</span></span>

<span data-ttu-id="a747c-117">Il layout automatico consente di modificare automaticamente le dimensioni di un controllo in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a747c-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="a747c-118">Ad esempio, un controllo può cambiare in base alla lunghezza di una stringa.</span><span class="sxs-lookup"><span data-stu-id="a747c-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="a747c-119">Questa funzionalità consente ai localizzatori di tradurre la stringa senza dover ridimensionare il controllo per adattarlo al testo tradotto.</span><span class="sxs-lookup"><span data-stu-id="a747c-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="a747c-120">L'esempio seguente crea un pulsante con contenuto in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="a747c-120">The following example creates a button with English content.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

<span data-ttu-id="a747c-121">Nell'esempio, l'unica operazione da compiere per creare un pulsante in lingua spagnola è modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="a747c-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="a747c-122">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a747c-122">For example,</span></span>

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

<span data-ttu-id="a747c-123">Il grafico seguente mostra l'output degli esempi di codice:</span><span class="sxs-lookup"><span data-stu-id="a747c-123">The following graphic shows the output of the code samples:</span></span>

![Lo stesso pulsante con testo in lingue diverse](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="a747c-125">Layout automatico e standard di codifica</span><span class="sxs-lookup"><span data-stu-id="a747c-125">Automatic Layout and Coding Standards</span></span>

<span data-ttu-id="a747c-126">L'uso dell'approccio di layout automatico richiede un set di regole e standard di codifica e progettazione per produrre un'interfaccia utente completamente localizzabile.</span><span class="sxs-lookup"><span data-stu-id="a747c-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="a747c-127">Le linee guida riportate di seguito agevolano la codifica del layout automatico.</span><span class="sxs-lookup"><span data-stu-id="a747c-127">The following guidelines will aid your automatic layout coding.</span></span>

<span data-ttu-id="a747c-128">**Non usare posizioni assolute**</span><span class="sxs-lookup"><span data-stu-id="a747c-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="a747c-129">Non usare <xref:System.Windows.Controls.Canvas> perché posiziona gli elementi in modo assoluto.</span><span class="sxs-lookup"><span data-stu-id="a747c-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="a747c-130">Usare <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> e <xref:System.Windows.Controls.Grid> per posizionare i controlli.</span><span class="sxs-lookup"><span data-stu-id="a747c-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="a747c-131">Per una descrizione dei vari tipi di pannelli, vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a747c-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="a747c-132">**Non impostare dimensioni fisse per una finestra**</span><span class="sxs-lookup"><span data-stu-id="a747c-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="a747c-133">Usare <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a747c-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a747c-134">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a747c-134">For example:</span></span>

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="a747c-135">**Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="a747c-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="a747c-136">Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A> all'elemento radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a747c-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

  <span data-ttu-id="a747c-137">WPF offre un modo pratico per supportare layout orizzontali, bidirezionali e verticali.</span><span class="sxs-lookup"><span data-stu-id="a747c-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="a747c-138">Nel Framework di presentazione, è possibile usare la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> per definire il layout.</span><span class="sxs-lookup"><span data-stu-id="a747c-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="a747c-139">I modelli di direzione del flusso sono:</span><span class="sxs-lookup"><span data-stu-id="a747c-139">The flow-direction patterns are:</span></span>

  - <span data-ttu-id="a747c-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb): layout orizzontale per il latino, l'Asia orientale e così via.</span><span class="sxs-lookup"><span data-stu-id="a747c-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>

  - <span data-ttu-id="a747c-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb): bidirezionale per l'arabo, l'ebraico e così via.</span><span class="sxs-lookup"><span data-stu-id="a747c-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="a747c-142">**Usare tipi di carattere compositi invece di tipi di carattere fisici**</span><span class="sxs-lookup"><span data-stu-id="a747c-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="a747c-143">Con i tipi di carattere compositi non è necessario localizzare la proprietà <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="a747c-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="a747c-144">Gli sviluppatori possono usare uno dei tipi di carattere riportati di seguito oppure crearne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a747c-144">Developers can use one of the following fonts or create their own.</span></span>

  - <span data-ttu-id="a747c-145">Interfaccia utente globale</span><span class="sxs-lookup"><span data-stu-id="a747c-145">Global User Interface</span></span>
  - <span data-ttu-id="a747c-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="a747c-146">Global San Serif</span></span>
  - <span data-ttu-id="a747c-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="a747c-147">Global Serif</span></span>

<span data-ttu-id="a747c-148">**Aggiungi XML: lang**</span><span class="sxs-lookup"><span data-stu-id="a747c-148">**Add xml:lang**</span></span>

- <span data-ttu-id="a747c-149">Aggiungere l'attributo `xml:lang` nell'elemento radice dell'interfaccia utente, ad esempio `xml:lang="en-US"` per un'applicazione in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="a747c-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="a747c-150">Poiché i tipi di carattere composito utilizzano `xml:lang` per determinare il tipo di carattere da utilizzare, impostare questa proprietà per supportare scenari multilingue.</span><span class="sxs-lookup"><span data-stu-id="a747c-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a><span data-ttu-id="a747c-151">Layout automatico e griglie</span><span class="sxs-lookup"><span data-stu-id="a747c-151">Automatic Layout and Grids</span></span>

<span data-ttu-id="a747c-152">L'elemento <xref:System.Windows.Controls.Grid> è utile per il layout automatico perché consente agli sviluppatori di posizionare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="a747c-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="a747c-153">Un controllo <xref:System.Windows.Controls.Grid> è in grado di distribuire lo spazio disponibile tra gli elementi figlio, usando una disposizione di colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="a747c-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="a747c-154">Gli elementi dell'interfaccia utente possono estendersi su più celle ed è possibile disporre di griglie all'interno di griglie.</span><span class="sxs-lookup"><span data-stu-id="a747c-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="a747c-155">Le griglie sono utili perché consentono di creare e posizionare interfacce utente complesse.</span><span class="sxs-lookup"><span data-stu-id="a747c-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="a747c-156">L'esempio seguente illustra l'uso di una griglia per posizionare alcuni pulsanti e del testo.</span><span class="sxs-lookup"><span data-stu-id="a747c-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="a747c-157">Si noti che l'altezza e la larghezza delle celle sono impostate su <xref:System.Windows.GridUnitType.Auto>; Pertanto, la cella che contiene il pulsante con un'immagine viene modificata in base all'immagine.</span><span class="sxs-lookup"><span data-stu-id="a747c-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

<span data-ttu-id="a747c-158">La figura seguente illustra la griglia prodotta dal codice precedente.</span><span class="sxs-lookup"><span data-stu-id="a747c-158">The following graphic shows the grid produced by the previous code.</span></span>

<span data-ttu-id="a747c-159">Griglia di ![esempio griglia](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="a747c-159">![Grid example](./media/glob-grid.png "glob_grid") Grid</span></span>

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="a747c-160">Layout automatico e griglie basate sull'uso della proprietà IsSharedSizeScope</span><span class="sxs-lookup"><span data-stu-id="a747c-160">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>

<span data-ttu-id="a747c-161">Un elemento <xref:System.Windows.Controls.Grid> è utile nelle applicazioni localizzabili per creare controlli che si adattano al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a747c-161">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="a747c-162">In alcuni casi, tuttavia, può essere opportuno che i controlli mantengano una determinata dimensione indipendentemente dal contenuto.</span><span class="sxs-lookup"><span data-stu-id="a747c-162">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="a747c-163">Ad esempio, nei casi dei pulsanti "OK", "Annulla" e "Sfoglia", probabilmente non si vuole che le dimensioni si adattino al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a747c-163">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="a747c-164">In questo caso la proprietà associata <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> è utile per condividere le stesse dimensioni tra più elementi della griglia.</span><span class="sxs-lookup"><span data-stu-id="a747c-164">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="a747c-165">Nell'esempio seguente viene illustrato come condividere dati di ridimensionamento di colonne e righe tra più elementi <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="a747c-165">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> <span data-ttu-id="a747c-166">Per l'esempio di codice completo, vedere [condividere le proprietà di ridimensionamento tra le griglie](../controls/how-to-share-sizing-properties-between-grids.md).</span><span class="sxs-lookup"><span data-stu-id="a747c-166">For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a747c-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a747c-167">See also</span></span>

- [<span data-ttu-id="a747c-168">Globalizzazione per WPF</span><span class="sxs-lookup"><span data-stu-id="a747c-168">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="a747c-169">Utilizzare un layout automatico per creare un pulsante</span><span class="sxs-lookup"><span data-stu-id="a747c-169">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="a747c-170">Usare una griglia per il layout automatico</span><span class="sxs-lookup"><span data-stu-id="a747c-170">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
