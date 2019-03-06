---
title: Cenni generali sul controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 689094bda355f095c30d6cc2a462e6d0e630753b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378197"
---
# <a name="richtextbox-overview"></a>Cenni generali sul controllo RichTextBox
Il <xref:System.Windows.Controls.RichTextBox> controllo consente di visualizzare o modificare il contenuto di flusso, tra cui paragrafi, immagini, tabelle e altro ancora. Questo argomento vengono presentate le <xref:System.Windows.Controls.TextBox> classe e vengono forniti esempi su come usarlo in entrambe [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e C#.  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>Differenza tra un controllo TextBox e un controllo RichTextBox  
 Entrambe <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.TextBox> consentire agli utenti di modificare il testo, tuttavia, i due controlli vengono usati in scenari diversi. Oggetto <xref:System.Windows.Controls.RichTextBox> è una scelta migliore quando è necessario che l'utente deve modificare testo formattato, immagini, tabelle o altro contenuto avanzato. Ad esempio, la modifica di un documento, un articolo o un blog che richiede formattazione, immagini, e così via è più opportuno utilizzare un <xref:System.Windows.Controls.RichTextBox>. Oggetto <xref:System.Windows.Controls.TextBox> richiede meno risorse di sistema un <xref:System.Windows.Controls.RichTextBox> ed è ideale quando solo testo normale deve essere modificato (ad esempio l'utilizzo in form). Visualizzare [Cenni preliminari su TextBox](textbox-overview.md) per altre informazioni su <xref:System.Windows.Controls.TextBox>. La tabella seguente riepiloga le principali funzionalità di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox>.  
  
|Control|Controllo ortografico in tempo reale|Menu di scelta rapida|Formattazione di comandi, ad esempio <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B)|<xref:System.Windows.Documents.FlowDocument> contenuto, ad esempio immagini, paragrafi, tabelle e così via.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sì|Yes|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sì|Yes|Yes|Sì|  
  
 **Nota:** Sebbene <xref:System.Windows.Controls.TextBox> non supporta i comandi correlati, ad esempio di formattazione <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B), molti comandi di base sono supportati entrambi i controlli, ad esempio <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Le funzionalità della tabella precedente vengono illustrate in dettaglio più avanti.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>Creazione di un oggetto RichTextBox  
 Il codice seguente illustra come creare un <xref:System.Windows.Controls.RichTextBox> che un utente può modificare contenuto complesso.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 In particolare, modificare il contenuto un <xref:System.Windows.Controls.RichTextBox> è il contenuto del flusso. Tale contenuto può includere molti tipi di elementi, ad esempio testo formattato, immagini, elenchi e tabelle. Per informazioni approfondite sui documenti dinamici, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md). Per includere il contenuto di flusso, un <xref:System.Windows.Controls.RichTextBox> ospita un <xref:System.Windows.Documents.FlowDocument> oggetto contenente a sua volta il contenuto modificabile. Per illustrare il contenuto di flusso in un <xref:System.Windows.Controls.RichTextBox>, il codice seguente viene illustrato come creare un <xref:System.Windows.Controls.RichTextBox> con un paragrafo e testo in grassetto.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 La figura seguente illustra come viene eseguito il rendering dell'esempio.  
  
 ![RichTextBox con contenuto](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 Elementi quali <xref:System.Windows.Documents.Paragraph> e <xref:System.Windows.Documents.Bold> determinare come il contenuto all'interno di un <xref:System.Windows.Controls.RichTextBox> viene visualizzata. Quando un utente modifica <xref:System.Windows.Controls.RichTextBox> contenuto, viene cambiato questo contenuto di flusso. Per altre informazioni sulle funzionalità del contenuto di flusso e sul relativo uso, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md).  
  
 **Nota:** Flusso del contenuto all'interno di un <xref:System.Windows.Controls.RichTextBox> non si comporta esattamente come contenuto dinamico incluso in altri controlli. Ad esempio, non sono disponibili colonne in un <xref:System.Windows.Controls.RichTextBox> e pertanto comportamento di ridimensionamento non automatico. Inoltre, funzionalità incorporate quali ricerca, la modalità di visualizzazione, la navigazione e lo zoom non sono disponibili all'interno di un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>Controllo ortografico in tempo reale  
 È possibile abilitare controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Quando il controllo ortografico è attivato, viene visualizzata una riga rossa sotto le parole errate (vedere la figura seguente).  
  
 ![TextBox con controllo ortografico](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Per informazioni su come abilitare il controllo ortografico, vedere [Procedura: attivare il controllo ortografico in un controllo di modifica del testo](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>Menu di scelta rapida  
 Per impostazione predefinita, entrambe <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> dispone di un menu di scelta rapida visualizzato quando un utente fa clic all'interno del controllo. Il menu di scelta rapida consente all'utente di eseguire operazioni di Taglia, Copia o Incolla (vedere la figura seguente).  
  
 ![TextBox con menu di scelta rapida](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 È possibile creare un menu di scelta rapida personalizzato per ignorare quello predefinito. Per altre informazioni, vedere [ Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>Comandi di modifica  
 Comandi di modifica consentono agli utenti di formattare il contenuto modificabile all'interno di un <xref:System.Windows.Controls.RichTextBox>. Oltre a basic, comandi di modifica <xref:System.Windows.Controls.RichTextBox> include comandi di formattazione che <xref:System.Windows.Controls.TextBox> non supporta. Ad esempio, quando si modifica un <xref:System.Windows.Controls.RichTextBox>, un utente è stato possibile premere CTRL + B per attivare o disattivare la formattazione del testo in grassetto. Vedere <xref:System.Windows.Documents.EditingCommands> per un elenco completo di comandi disponibili. Oltre a usare i tasti di scelta rapida, è possibile associare i comandi ad altri controlli, quali i pulsanti. L'esempio seguente illustra la procedura per creare una barra degli strumenti semplice, che l'utente potrà usare per modificare la formattazione del testo.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 La figura seguente illustra la visualizzazione dell'esempio.  
  
 ![RichTextBox con barra degli strumenti](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Rilevare le modifiche di contenuto  
 In genere il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento deve essere usato per rilevare ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> viene modificato anziché <xref:System.Windows.UIElement.KeyDown> come è prevedibile. Per un esempio, vedere [Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>Salvare, caricare e stampare il contenuto di RichTextBox  
 Nell'esempio seguente viene illustrato come salvare il contenuto di un <xref:System.Windows.Controls.RichTextBox> in un file, caricarlo nuovamente nel <xref:System.Windows.Controls.RichTextBox>e stampare il contenuto. Di seguito è indicato il markup per l'esempio.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Di seguito è indicato il code-behind per l'esempio.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedure relative alle proprietà](richtextbox-how-to-topics.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
