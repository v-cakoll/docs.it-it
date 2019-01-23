---
title: Cenni preliminari sulla classe TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: c33edcf98f13e637d41de41618e5e6364c69613a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556012"
---
# <a name="textbox-overview"></a>Cenni preliminari sulla classe TextBox
Il <xref:System.Windows.Controls.TextBox> classe consente di visualizzare o modificare testo non formattato. Un uso comune di un <xref:System.Windows.Controls.TextBox> consiste nel modificare testo non formattato in un form. Ad esempio, un modulo che richiede il nome dell'utente, numero di telefono e così via utilizzerebbe <xref:System.Windows.Controls.TextBox> controlli per input di testo. Questo argomento vengono presentate le <xref:System.Windows.Controls.TextBox> classe e vengono forniti esempi su come usarlo in entrambe [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e C#.  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>Differenza tra un controllo TextBox e un controllo RichTextBox  
 Entrambe <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> consentire agli utenti di input di testo, ma i due controlli vengono usati per scenari diversi. Oggetto <xref:System.Windows.Controls.TextBox> richiede meno risorse di sistema un <xref:System.Windows.Controls.RichTextBox> pertanto è ideale quando occorre modificare solo testo normale (ad esempio, l'utilizzo in un modulo). Oggetto <xref:System.Windows.Controls.RichTextBox> è una scelta migliore quando è necessario che l'utente deve modificare testo formattato, immagini, tabelle o su altri contenuta. Ad esempio, la modifica di un documento, un articolo o un blog che richiede formattazione, immagini, e così via è più opportuno utilizzare un <xref:System.Windows.Controls.RichTextBox>. La tabella seguente riepiloga le principali funzionalità del <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBox>.  
  
|Control|Controllo ortografico in tempo reale|Menu di scelta rapida|Formattazione di comandi, ad esempio <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B)|<xref:System.Windows.Documents.FlowDocument> contenuto, ad esempio immagini, paragrafi, tabelle e così via.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Yes|Yes|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Yes|Yes|Sì (vedere [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|Sì (vedere [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|  
  
> [!NOTE]
>  Sebbene <xref:System.Windows.Controls.TextBox> esegue i comandi non supportano modifica correlati alla formattazione, ad esempio <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B), molti comandi di base sono supportati entrambi i controlli, ad esempio <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Per altre informazioni, vedere <xref:System.Windows.Documents.EditingCommands>.  
  
 Funzionalità supportate dalle <xref:System.Windows.Controls.TextBox> sono illustrati nelle sezioni seguenti. Per altre informazioni sulle <xref:System.Windows.Controls.RichTextBox>, vedere [preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Controllo ortografico in tempo reale  
 È possibile abilitare il controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Quando il controllo ortografico è attivato, viene visualizzata una riga rossa sotto le parole errate (vedere la figura seguente).  
  
 ![TextBox con controllo ortografico](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Per informazioni su come abilitare il controllo ortografico, vedere [Procedura: attivare il controllo ortografico in un controllo di modifica del testo](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Menu di scelta rapida  
 Per impostazione predefinita, entrambe <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> dispone di un menu di scelta rapida visualizzato quando un utente fa clic all'interno del controllo. Il menu di scelta rapida consente all'utente di tagliare, copiare o incollare (vedere la figura seguente).  
  
 ![TextBox con menu di scelta rapida](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 È possibile creare un menu di scelta rapida personalizzato per ignorare il comportamento predefinito. Per altre informazioni, vedere [Utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Creazione di caselle di testo  
 Oggetto <xref:System.Windows.Controls.TextBox> può essere una singola riga in altezza o più righe. Una singola riga <xref:System.Windows.Controls.TextBox> è migliore se si deve immettere piccole quantità di testo normale (ad esempio, "Nome", "Numero di telefono" e altro in un modulo). Nell'esempio seguente viene illustrato come creare una singola riga <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 È anche possibile creare un <xref:System.Windows.Controls.TextBox> che consente all'utente di immettere più righe di testo. Ad esempio, se il formato richiesto per una breve biografia dell'utente, è preferibile usare un <xref:System.Windows.Controls.TextBox> che supporta più righe di testo. Nell'esempio seguente viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanda automaticamente per inserire più righe di testo.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Impostando il <xref:System.Windows.Controls.TextBox.TextWrapping%2A> dell'attributo `Wrap` fa sì che il testo a capo a una nuova riga quando il bordo del <xref:System.Windows.Controls.TextBox> controllo viene raggiunto, si espande automaticamente il <xref:System.Windows.Controls.TextBox> controllo per includere una nuova riga, se necessario.  
  
 Impostando il <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> dell'attributo `true` fa sì che una nuova riga deve essere inserito quando viene premuto il tasto INVIO, espande automaticamente il <xref:System.Windows.Controls.TextBox> per inserire una nuova riga, se necessario.  
  
 Il <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento per il <xref:System.Windows.Controls.TextBox>, in modo che il contenuto del <xref:System.Windows.Controls.TextBox> se è possibile scorrere il <xref:System.Windows.Controls.TextBox> espande oltre la dimensione della cornice o finestra che lo racchiude.  
  
 Per altre informazioni sulle diverse attività correlate all'utilizzo di un <xref:System.Windows.Controls.TextBox>, vedere [procedure](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Rilevare le modifiche di contenuto  
 In genere il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento deve essere usato per rilevare ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> viene modificato, anziché <xref:System.Windows.UIElement.KeyDown> come è prevedibile. Per un esempio, vedere [Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Vedere anche
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)
- [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
