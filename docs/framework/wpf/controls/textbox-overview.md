---
title: Cenni preliminari sulla classe TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: bb03d09b1730f4a8d607773f9024eee4f125e2c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557771"
---
# <a name="textbox-overview"></a>Cenni preliminari sulla classe TextBox
La <xref:System.Windows.Controls.TextBox> classe consente di visualizzare o modificare testo non formattato. Un utilizzo comune di un <xref:System.Windows.Controls.TextBox> consiste nel modificare testo non formattato in un form. Ad esempio, un modulo che richiede il nome dell'utente, numero di telefono, e così via utilizzerebbe <xref:System.Windows.Controls.TextBox> controlli per input di testo. Questo argomento vengono presentate le <xref:System.Windows.Controls.TextBox> classe e vengono forniti esempi su come utilizzarla in entrambi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e c#.  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>Differenza tra un controllo TextBox e un controllo RichTextBox  
 Entrambi <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> consentire agli utenti di testo di input, ma i due controlli vengono utilizzati per diversi scenari. Oggetto <xref:System.Windows.Controls.TextBox> richiede meno risorse di sistema un <xref:System.Windows.Controls.RichTextBox> è ideale per la modifica di solo testo normale (ad esempio, di utilizzo in un formato). Oggetto <xref:System.Windows.Controls.RichTextBox> è una scelta migliore quando è necessario che all'utente di modificare il testo formattato, immagini, tabelle o altri supportati del contenuto. Ad esempio, la modifica di un documento, un articolo o blog che richiede una formattazione, immagini, e così via è più opportuno utilizzare un <xref:System.Windows.Controls.RichTextBox>. Nella tabella seguente sono riepilogate le funzionalità principali di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBox>.  
  
|Control|Controllo ortografico in tempo reale|Menu di scelta rapida|Comandi di formattazione quale <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B)|<xref:System.Windows.Documents.FlowDocument> contenuto, ad esempio immagini, paragrafi, tabelle e così via.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Yes|Sì|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Yes|Yes|Sì (vedere [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|Sì (vedere [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|  
  
> [!NOTE]
>  Sebbene <xref:System.Windows.Controls.TextBox> fa comandi non supportano la formattazione modifica correlati come <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B), molti comandi di base sono supportati da entrambi i controlli, ad esempio <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Per altre informazioni, vedere <xref:System.Windows.Documents.EditingCommands>.  
  
 Funzionalità supportate dalle <xref:System.Windows.Controls.TextBox> vengono trattati nelle sezioni seguenti. Per ulteriori informazioni su <xref:System.Windows.Controls.RichTextBox>, vedere [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Controllo ortografico in tempo reale  
 È possibile abilitare il controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Quando il controllo ortografico è attivato, viene visualizzata una riga rossa sotto le parole errate (vedere la figura seguente).  
  
 ![TextBox con controllo ortografico](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Per informazioni su come abilitare il controllo ortografico, vedere [Procedura: attivare il controllo ortografico in un controllo di modifica del testo](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Menu di scelta rapida  
 Per impostazione predefinita, entrambi <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> dispone di un menu di scelta rapida che viene visualizzata quando l'utente fa clic all'interno del controllo. Il menu di scelta rapida consente all'utente di tagliare, copiare o incollare (vedere la figura seguente).  
  
 ![TextBox con menu di scelta rapida](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 È possibile creare un menu di scelta rapida personalizzato per ignorare il comportamento predefinito. Per altre informazioni, vedere [Utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Creazione di caselle di testo  
 Oggetto <xref:System.Windows.Controls.TextBox> può essere una singola riga in altezza o comprendere più righe. Una singola riga <xref:System.Windows.Controls.TextBox> è ottimale per l'immissione di piccole quantità di testo normale (ovvero "Nome", "Numero di telefono" e altro in un modulo). Nell'esempio seguente viene illustrato come creare una singola riga <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 È inoltre possibile creare un <xref:System.Windows.Controls.TextBox> che consente all'utente di immettere più righe di testo. Ad esempio, se il formato richiesto di un biografici dell'utente, si desidera utilizzare un <xref:System.Windows.Controls.TextBox> che supporta più righe di testo. Nell'esempio seguente viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espande automaticamente per inserire più righe di testo.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Impostazione di <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attributo `Wrap` il testo viene disposto in una nuova riga quando il bordo del <xref:System.Windows.Controls.TextBox> controllo viene raggiunto, si espande automaticamente il <xref:System.Windows.Controls.TextBox> controllo per inserire una nuova riga, se necessario.  
  
 L'impostazione di <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attributo `true` una nuova riga da inserire quando viene premuto il tasto INVIO, espande automaticamente il <xref:System.Windows.Controls.TextBox> per inserire una nuova riga, se necessario.  
  
 Il <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento di <xref:System.Windows.Controls.TextBox>, in modo che il contenuto del <xref:System.Windows.Controls.TextBox> se è possibile scorrere il <xref:System.Windows.Controls.TextBox> si espanda oltre il frame o la finestra che lo contiene.  
  
 Per ulteriori informazioni sulle diverse attività correlate all'utilizzo di un <xref:System.Windows.Controls.TextBox>, vedere [procedure](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Rilevare le modifiche di contenuto  
 In genere il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento deve essere utilizzato per rilevare ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> viene modificato, anziché <xref:System.Windows.UIElement.KeyDown> come previsto. Per un esempio, vedere [Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
