---
title: Cenni preliminari sulla classe TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 86b2cf8cb0c72186fd92bdad0af6bf5bd3fa9f3f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174432"
---
# <a name="textbox-overview"></a>Cenni preliminari sulla classe TextBox
La <xref:System.Windows.Controls.TextBox> classe consente di visualizzare o modificare testo non formattato. Un uso comune di un oggetto <xref:System.Windows.Controls.TextBox> consiste nel modificare il testo non formattato in un form. Ad esempio, un modulo che richiede il nome dell'utente, il numero di telefono e così via utilizzerà i <xref:System.Windows.Controls.TextBox> controlli per l'input di testo. In questo argomento viene introdotta la <xref:System.Windows.Controls.TextBox> classe e vengono forniti esempi di come utilizzarla sia in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che in C#.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>Differenza tra un controllo TextBox e un controllo RichTextBox  
 Sia <xref:System.Windows.Controls.TextBox> che <xref:System.Windows.Controls.RichTextBox> consentono agli utenti di immettere testo, ma i due controlli vengono usati per scenari diversi. Un <xref:System.Windows.Controls.TextBox> richiede un minor numero di risorse di sistema <xref:System.Windows.Controls.RichTextBox> , quindi è ideale quando è necessario modificare solo testo normale, ovvero l'utilizzo in un modulo. Una <xref:System.Windows.Controls.RichTextBox> è la scelta migliore quando è necessario che l'utente modifichi testo formattato, immagini, tabelle o altro contenuto supportato. Ad esempio, la modifica di un documento, di un articolo o di un blog che richiede la formattazione, le immagini e così via viene eseguita con maggiore utilizzo <xref:System.Windows.Controls.RichTextBox> . Nella tabella seguente sono riepilogate le principali funzionalità di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> .  
  
|Control|Controllo ortografico in tempo reale|Menu di scelta rapida|Formattazione di comandi come <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument>contenuto come immagini, paragrafi, tabelle e così via.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sì|Sì|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sì|Sì|Sì (vedere [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md))|Sì (vedere [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md))|  
  
> [!NOTE]
> Sebbene non <xref:System.Windows.Controls.TextBox> supporti la formattazione dei comandi di modifica correlati <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> , ad esempio (Ctr + B), molti comandi di base sono supportati da entrambi i controlli, ad esempio <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> . Per altre informazioni, vedere <xref:System.Windows.Documents.EditingCommands>.  
  
 Le funzionalità supportate da <xref:System.Windows.Controls.TextBox> sono descritte nelle sezioni riportate di seguito. Per ulteriori informazioni su <xref:System.Windows.Controls.RichTextBox> , vedere [Cenni preliminari su RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Controllo ortografico in tempo reale  
 È possibile abilitare controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> . Quando il controllo ortografico è attivato, viene visualizzata una riga rossa sotto le parole errate (vedere la figura seguente).  
  
 ![TextBox con controllo ortografico&#45;](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Per informazioni su come abilitare il controllo ortografico, vedere [Procedura: attivare il controllo ortografico in un controllo di modifica del testo](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Menu di scelta rapida  
 Per impostazione predefinita, <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> dispongono di un menu di scelta rapida che viene visualizzato quando un utente fa clic con il pulsante destro del mouse all'interno del controllo. Il menu di scelta rapida consente all'utente di tagliare, copiare o incollare (vedere la figura seguente).  
  
 ![TextBox con menu di scelta rapida](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 È possibile creare un menu di scelta rapida personalizzato per ignorare il comportamento predefinito. Per altre informazioni, vedere [Utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>Creazione di caselle di testo  
 Un oggetto <xref:System.Windows.Controls.TextBox> può essere costituito da una singola riga in altezza o da più righe. Una singola riga <xref:System.Windows.Controls.TextBox> è ideale per inserire piccole quantità di testo normale, ad esempio "nome", "numero di telefono" e così via, in un modulo. Nell'esempio seguente viene illustrato come creare una singola riga <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 È anche possibile creare un oggetto <xref:System.Windows.Controls.TextBox> che consente all'utente di immettere più righe di testo. Se, ad esempio, il form richiede un abbozzo biografico dell'utente, è consigliabile usare un <xref:System.Windows.Controls.TextBox> che supporta più righe di testo. Nell'esempio seguente viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espande automaticamente per supportare più righe di testo.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 <xref:System.Windows.Controls.TextBox.TextWrapping%2A>Se si imposta l'attributo su `Wrap` , il testo viene sottoposto a wrapping in una nuova riga quando viene raggiunto il bordo del <xref:System.Windows.Controls.TextBox> controllo, espandendo automaticamente il <xref:System.Windows.Controls.TextBox> controllo in modo da includere la stanza per una nuova riga, se necessario.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Se si imposta l'attributo su `true` , viene inserita una nuova riga quando viene premuto il tasto restituito, una volta che si espande automaticamente per <xref:System.Windows.Controls.TextBox> includere la stanza per una nuova riga, se necessario.  
  
 L' <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento a <xref:System.Windows.Controls.TextBox> , in modo che sia possibile scorrere il contenuto di <xref:System.Windows.Controls.TextBox> se l'oggetto <xref:System.Windows.Controls.TextBox> si espande oltre le dimensioni del frame o della finestra che lo racchiude.  
  
 Per ulteriori informazioni sulle diverse attività associate all'utilizzo di un <xref:System.Windows.Controls.TextBox> , vedere [procedure](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>Rilevare le modifiche di contenuto  
 In genere <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> , l'evento deve essere usato per rilevare ogni volta che il testo in un oggetto <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> viene modificato, anziché <xref:System.Windows.UIElement.KeyDown> come previsto. Per un esempio, vedere [Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](textbox-how-to-topics.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
