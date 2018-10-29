---
title: Cenni preliminari sull'utilizzo del layout automatico
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: d6ed0da9be32a4a4de4111acfb2d347b7bd5096d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201556"
---
# <a name="use-automatic-layout-overview"></a>Cenni preliminari sull'utilizzo del layout automatico
In questo argomento illustra le linee guida per gli sviluppatori su come scrivere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le applicazioni con localizzabile [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. In passato, la localizzazione di un'interfaccia utente era un processo molto tempo. Ogni lingua dell'interfaccia utente è stato adattato per richiedeva modifiche pixel per pixel. Oggi, con la progettazione e standard, di codifica corretti [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] può essere costruito in modo che i localizzatori hanno ridimensionamento e riposizionamento a scopo. L'approccio alla scrittura di applicazioni che è possibile ridimensionare e riposizionare con maggiore semplicità viene definito layout automatico e può essere ottenuta utilizzando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progettazione dell'applicazione.  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Vantaggi dell'uso del layout automatico  
 Poiché il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di presentazione è potente e flessibile, offre la possibilità di layout di elementi in un'applicazione che può essere modificata per soddisfare i requisiti di lingue diverse. L'elenco seguente indica alcuni vantaggi del layout automatico.  

-   Interfaccia utente viene visualizzata correttamente in qualsiasi linguaggio.  

-   Riduce l'esigenza di ulteriori modifiche alla posizione e alle dimensioni dei controlli dopo la traduzione del testo.  
  
-   Riduce l'esigenza di ulteriori modifiche alle dimensioni delle finestre.  

-   Layout dell'interfaccia utente viene visualizzato correttamente in qualsiasi linguaggio.  

-   La localizzazione può essere ridotta a semplici attività che vanno poco oltre la traduzione delle stringhe.  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>Layout automatico e controlli  
 Il layout automatico consente di modificare automaticamente le dimensioni di un controllo in un'applicazione. Ad esempio, un controllo può cambiare in base alla lunghezza di una stringa. Questa funzionalità consente ai localizzatori di tradurre la stringa senza dover ridimensionare il controllo per adattarlo al testo tradotto. L'esempio seguente crea un pulsante con contenuto in lingua inglese.  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 Nell'esempio, l'unica operazione da compiere per creare un pulsante in lingua spagnola è modificare il testo. Ad esempio,  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 La figura seguente mostra l'output degli esempi di codice.  
  
 ![Lo stesso pulsante con testo in lingue diverse](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Pulsante a ridimensionamento automatico  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>Layout automatico e standard di codifica  
 Usa l'approccio di layout automatico richiede un set di codice e gli standard di progettazione e le regole per produrre un'interfaccia utente completamente localizzabile. Le linee guida riportate di seguito agevolano la codifica del layout automatico.  

**Non usare posizioni assolute**

- Non usare <xref:System.Windows.Controls.Canvas> perché gli elementi vengono posizionati in modo assoluto.

- Uso <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, e <xref:System.Windows.Controls.Grid> per posizionare i controlli.

Per una discussione sui vari tipi di pannelli, vedere [pannelli Panoramica](../../../../docs/framework/wpf/controls/panels-overview.md).

**Non si imposta una dimensione fissa per una finestra**

- Usare <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>. Ad esempio:

   [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A> all'elemento radice dell'applicazione.

   WPF offre un modo pratico per supportare orizzontali, bidirezionale e layout verticale. Nel framework della presentazione di <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà può essere utilizzata per definire il layout. I modelli di direzione del flusso sono:
   
     - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb)-layout orizzontale per latino, asiatico e così via.
     
     - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb)-bidirezionale per arabo, ebraico e così via.

**Usare tipi di carattere compositi anziché tipi di carattere fisici**

- Con tipi di carattere compositi, il <xref:System.Windows.Controls.Control.FontFamily%2A> proprietà non deve essere localizzata.

- Gli sviluppatori possono usare uno dei tipi di carattere riportati di seguito oppure crearne uno personalizzato.

   - Interfaccia utente globale
   - Global San Serif
   - Global Serif

**Aggiungere XML: lang**

- Aggiungere il `xml:lang` attributo nell'elemento radice dell'interfaccia utente, ad esempio `xml:lang="en-US"` per un'applicazione in lingua inglese.

- Perché usare tipi di carattere compositi `xml:lang` per determinare il tipo di carattere da usare, impostare questa proprietà per supportare scenari multilingue.

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Layout automatico e griglie  
 Il <xref:System.Windows.Controls.Grid> elemento, è utile per il layout automatico poiché consente a uno sviluppatore di posizionare gli elementi. Oggetto <xref:System.Windows.Controls.Grid> controllo è in grado di distribuire lo spazio disponibile tra gli elementi figlio, usando una disposizione di riga e colonna. Elementi dell'interfaccia utente possono estendersi su più celle, ed è possibile inserire griglie all'interno di griglie. Griglie sono utili perché consentono di creare e posizionare l'interfaccia utente complessa. L'esempio seguente illustra l'uso di una griglia per posizionare alcuni pulsanti e del testo. Si noti che l'altezza e la larghezza delle celle sono impostate per <xref:System.Windows.GridUnitType.Auto>; di conseguenza, la cella che contiene il pulsante con un'immagine viene modificata per adattarsi all'immagine.  

 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 La figura seguente illustra la griglia prodotta dal codice precedente.  
  
 ![Esempio di Grid](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Layout automatico e griglie basate sull'uso della proprietà IsSharedSizeScope  
 Oggetto <xref:System.Windows.Controls.Grid> elemento è utile nelle applicazioni localizzabili per creare controlli che vengono modificati per adattarsi al contenuto. In alcuni casi, tuttavia, può essere opportuno che i controlli mantengano una determinata dimensione indipendentemente dal contenuto. Ad esempio, nei casi dei pulsanti "OK", "Annulla" e "Sfoglia", probabilmente non si vuole che le dimensioni si adattino al contenuto. In questo caso il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> proprietà associata è utile per condividere le stesse dimensioni tra più elementi grid. Nell'esempio seguente viene illustrato come condividere colonne e righe di dati tra più sulle dimensioni <xref:System.Windows.Controls.Grid> elementi.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Nota** per l'esempio di codice completo, vedere [condivisione di proprietà di ridimensionamento tra griglie](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione per WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Utilizzare un layout automatico per creare un pulsante](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Usare una griglia per il layout automatico](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
