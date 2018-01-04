---
title: Cenni preliminari sull'utilizzo del layout automatico
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75066b59d0f3a686c66fdbdd187ba4c18e786e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="use-automatic-layout-overview"></a>Cenni preliminari sull'utilizzo del layout automatico
Questo argomento vengono presentate le linee guida per gli sviluppatori su come scrivere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni con localizzabili [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. In passato, la localizzazione di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] era un processo molto tempo. Ogni lingua che il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è stato adattato richiedeva modifiche pixel per pixel. Oggi, con la progettazione e di destra standard di codifica, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] può essere costruito in modo che i localizzatori hanno ridimensionamento e riposizionamento scopo. L'approccio alla scrittura di applicazioni che possono essere più facilmente ridimensionare e riposizionare viene chiamato il layout automatico e può essere ottenuta usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progettazione di applicazioni.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Vantaggi dell'uso del layout automatico  
 Poiché il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di presentazione è potente e flessibile, offre la possibilità per gli elementi di layout in un'applicazione che può essere modificata per soddisfare i requisiti delle diverse lingue. L'elenco seguente indica alcuni vantaggi del layout automatico.  
  
-   L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene visualizzata correttamente in qualsiasi lingua.  
  
-   Riduce l'esigenza di ulteriori modifiche alla posizione e alle dimensioni dei controlli dopo la traduzione del testo.  
  
-   Riduce l'esigenza di ulteriori modifiche alle dimensioni delle finestre.  
  
-   Il rendering del layout dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene eseguito correttamente in qualsiasi lingua.  
  
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
 Usa l'approccio di layout automatico richiede un set di standard di codifica e di progettazione e le regole per produrre un completamente localizzabile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Le linee guida riportate di seguito agevolano la codifica del layout automatico.  
  
|Standard di codifica|Descrizione|  
|----------------------|-----------------|  
|Non usare posizioni assolute.|-Non usare <xref:System.Windows.Controls.Canvas> perché posizionamento assoluto degli elementi.<br />-Utilizzare <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, e <xref:System.Windows.Controls.Grid> per posizionare i controlli.<br />-Per informazioni sui diversi tipi di pannelli, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|Non impostare una dimensione fissa per una finestra.|-Utilizzare <xref:System.Windows.Window.SizeToContent%2A>.<br />- Ad esempio:<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A>.|<ul><li>Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A> all'elemento radice dell'applicazione.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un modo pratico per supportare layout orizzontali, bidirezionale e verticali. Nel framework della presentazione di <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà può essere utilizzata per definire il layout. I modelli di direzione del flusso sono:<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight>(LrTb), un layout orizzontale per alfabeto latino, Asia orientale e così via.</li><li><xref:System.Windows.FlowDirection.RightToLeft>(RlTb), ovvero bidirezionale per arabo, ebraico e così via.</li></ul></li></ul>|  
|Usare tipi di carattere compositi anziché tipi di carattere fisici.|<ul><li>Con i tipi di carattere compositi di <xref:System.Windows.Controls.Control.FontFamily%2A> proprietà non devono essere localizzati.</li><li>Gli sviluppatori possono usare uno dei tipi di carattere riportati di seguito oppure crearne uno personalizzato.<br /><br /> <ul><li>Interfaccia utente globale</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Aggiungere xml:lang.|-Aggiungere la `xml:lang` attributo nell'elemento radice del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ad esempio `xml:lang="en-US"` per un'applicazione in lingua inglese.<br />-Poiché utilizzano tipi di carattere compositi `xml:lang` per determinare il tipo di carattere da utilizzare, impostare questa proprietà per supportare scenari multilingue.|  
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Layout automatico e griglie  
 Il <xref:System.Windows.Controls.Grid> elemento, è utile per il layout automatico perché consente agli sviluppatori di posizionare gli elementi. Oggetto <xref:System.Windows.Controls.Grid> controllo è in grado di distribuire lo spazio disponibile tra gli elementi figlio, utilizzando una disposizione di riga e colonna. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi possono estendersi su più celle, ed è possibile inserire griglie all'interno di griglie. Le griglie sono utili perché consentono di creare e posizionare complessi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. L'esempio seguente illustra l'uso di una griglia per posizionare alcuni pulsanti e del testo. Si noti che l'altezza e la larghezza delle celle sono impostate per <xref:System.Windows.GridUnitType.Auto>; pertanto, la cella che contiene il pulsante con un'immagine adattato l'immagine.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 La figura seguente illustra la griglia prodotta dal codice precedente.  
  
 ![Esempio di Grid](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Layout automatico e griglie basate sull'uso della proprietà IsSharedSizeScope  
 Oggetto <xref:System.Windows.Controls.Grid> elemento è utile nelle applicazioni localizzabili per creare controlli che vengono modificati per adattarsi al contenuto. In alcuni casi, tuttavia, può essere opportuno che i controlli mantengano una determinata dimensione indipendentemente dal contenuto. Ad esempio, nei casi dei pulsanti "OK", "Annulla" e "Sfoglia", probabilmente non si vuole che le dimensioni si adattino al contenuto. In questo caso il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> proprietà associata è utile per condividere le stesse dimensioni tra più elementi di griglia. Nell'esempio seguente viene illustrato come condividere dati tra più sulle dimensioni di riga e colonna <xref:System.Windows.Controls.Grid> elementi.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Nota** per l'esempio di codice completo, vedere [condivisione proprietà ridimensionamento tra griglie](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione per WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Utilizzare un layout automatico per creare un pulsante](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Usare una griglia per il layout automatico](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
