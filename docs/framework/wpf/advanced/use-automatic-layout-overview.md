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
# <a name="use-automatic-layout-overview"></a>Cenni preliminari sull'utilizzo del layout automatico

In questo argomento vengono presentate le linee guida per gli sviluppatori su come scrivere applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con interfacce utente localizzabili (UI). In passato, la localizzazione di un'interfaccia utente era un processo che richiedeva molto tempo. Ogni lingua in cui l'interfaccia utente è stata adattata per la regolazione del pixel è necessaria. Oggi, con la progettazione corretta e gli standard di codifica corretti, le interfacce utente possono essere costruite in modo che i localizzatori abbiano un minor ridimensionamento e un riposizionamento. L'approccio alla scrittura di applicazioni che possono essere ridimensionate e riposizionate più facilmente viene definito layout automatico e può essere eseguito utilizzando la progettazione di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a>Vantaggi dell'uso del layout automatico

Poiché il sistema di presentazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è potente e flessibile, offre la possibilità di applicare il layout degli elementi di un'applicazione che possono essere modificati in base ai requisiti di lingue diverse. L'elenco seguente indica alcuni vantaggi del layout automatico.

- L'interfaccia utente viene visualizzata correttamente in qualsiasi lingua.

- Riduce l'esigenza di ulteriori modifiche alla posizione e alle dimensioni dei controlli dopo la traduzione del testo.

- Riduce l'esigenza di ulteriori modifiche alle dimensioni delle finestre.

- Il layout dell'interfaccia utente viene visualizzato correttamente in qualsiasi lingua.

- La localizzazione può essere ridotta a semplici attività che vanno poco oltre la traduzione delle stringhe.

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a>Layout automatico e controlli

Il layout automatico consente di modificare automaticamente le dimensioni di un controllo in un'applicazione. Ad esempio, un controllo può cambiare in base alla lunghezza di una stringa. Questa funzionalità consente ai localizzatori di tradurre la stringa senza dover ridimensionare il controllo per adattarlo al testo tradotto. L'esempio seguente crea un pulsante con contenuto in lingua inglese.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

Nell'esempio, l'unica operazione da compiere per creare un pulsante in lingua spagnola è modificare il testo. Ad esempio,

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

Il grafico seguente mostra l'output degli esempi di codice:

![Lo stesso pulsante con testo in lingue diverse](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a>Layout automatico e standard di codifica

L'uso dell'approccio di layout automatico richiede un set di regole e standard di codifica e progettazione per produrre un'interfaccia utente completamente localizzabile. Le linee guida riportate di seguito agevolano la codifica del layout automatico.

**Non usare posizioni assolute**

- Non usare <xref:System.Windows.Controls.Canvas> perché posiziona gli elementi in modo assoluto.

- Usare <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> e <xref:System.Windows.Controls.Grid> per posizionare i controlli.

Per una descrizione dei vari tipi di pannelli, vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md).

**Non impostare dimensioni fisse per una finestra**

- Usare <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>. Esempio:

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- Aggiungere un <xref:System.Windows.FrameworkElement.FlowDirection%2A> all'elemento radice dell'applicazione.

  WPF offre un modo pratico per supportare layout orizzontali, bidirezionali e verticali. Nel Framework di presentazione, è possibile usare la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> per definire il layout. I modelli di direzione del flusso sono:

  - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb): layout orizzontale per il latino, l'Asia orientale e così via.

  - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb): bidirezionale per l'arabo, l'ebraico e così via.

**Usare tipi di carattere compositi invece di tipi di carattere fisici**

- Con i tipi di carattere compositi non è necessario localizzare la proprietà <xref:System.Windows.Controls.Control.FontFamily%2A>.

- Gli sviluppatori possono usare uno dei tipi di carattere riportati di seguito oppure crearne uno personalizzato.

  - Interfaccia utente globale
  - Global San Serif
  - Global Serif

**Aggiungi XML: lang**

- Aggiungere l'attributo `xml:lang` nell'elemento radice dell'interfaccia utente, ad esempio `xml:lang="en-US"` per un'applicazione in lingua inglese.

- Poiché i tipi di carattere composito utilizzano `xml:lang` per determinare il tipo di carattere da utilizzare, impostare questa proprietà per supportare scenari multilingue.

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a>Layout automatico e griglie

L'elemento <xref:System.Windows.Controls.Grid> è utile per il layout automatico perché consente agli sviluppatori di posizionare gli elementi. Un controllo <xref:System.Windows.Controls.Grid> è in grado di distribuire lo spazio disponibile tra gli elementi figlio, usando una disposizione di colonne e righe. Gli elementi dell'interfaccia utente possono estendersi su più celle ed è possibile disporre di griglie all'interno di griglie. Le griglie sono utili perché consentono di creare e posizionare interfacce utente complesse. L'esempio seguente illustra l'uso di una griglia per posizionare alcuni pulsanti e del testo. Si noti che l'altezza e la larghezza delle celle sono impostate su <xref:System.Windows.GridUnitType.Auto>; Pertanto, la cella che contiene il pulsante con un'immagine viene modificata in base all'immagine.

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

La figura seguente illustra la griglia prodotta dal codice precedente.

Griglia di ![esempio griglia](./media/glob-grid.png "glob_grid")

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Layout automatico e griglie basate sull'uso della proprietà IsSharedSizeScope

Un elemento <xref:System.Windows.Controls.Grid> è utile nelle applicazioni localizzabili per creare controlli che si adattano al contenuto. In alcuni casi, tuttavia, può essere opportuno che i controlli mantengano una determinata dimensione indipendentemente dal contenuto. Ad esempio, nei casi dei pulsanti "OK", "Annulla" e "Sfoglia", probabilmente non si vuole che le dimensioni si adattino al contenuto. In questo caso la proprietà associata <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> è utile per condividere le stesse dimensioni tra più elementi della griglia. Nell'esempio seguente viene illustrato come condividere dati di ridimensionamento di colonne e righe tra più elementi <xref:System.Windows.Controls.Grid>.

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> Per l'esempio di codice completo, vedere [condividere le proprietà di ridimensionamento tra le griglie](../controls/how-to-share-sizing-properties-between-grids.md).

## <a name="see-also"></a>Vedere anche

- [Globalizzazione per WPF](globalization-for-wpf.md)
- [Utilizzare un layout automatico per creare un pulsante](how-to-use-automatic-layout-to-create-a-button.md)
- [Usare una griglia per il layout automatico](how-to-use-a-grid-for-automatic-layout.md)
