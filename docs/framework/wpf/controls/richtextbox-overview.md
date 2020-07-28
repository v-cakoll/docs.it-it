---
title: Cenni generali sul controllo RichTextBox
description: Informazioni sul modo in cui il controllo Windows Presentation Foundation RichTextBox consente agli utenti di visualizzare o modificare contenuti come testo, immagini e tabelle. Vedere esempi di XAML e C#.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 525e27f9602136c68f160c738fd1c92ea761536c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166243"
---
# <a name="richtextbox-overview"></a>Cenni generali sul controllo RichTextBox

Il <xref:System.Windows.Controls.RichTextBox> controllo consente di visualizzare o modificare il contenuto del flusso, inclusi paragrafi, immagini, tabelle e altro ancora. In questo argomento viene introdotta la <xref:System.Windows.Controls.TextBox> classe e vengono forniti esempi di come utilizzarla sia in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che in C#.

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a>Differenza tra un controllo TextBox e un controllo RichTextBox

Sia <xref:System.Windows.Controls.RichTextBox> che <xref:System.Windows.Controls.TextBox> consentono agli utenti di modificare il testo, tuttavia, i due controlli vengono usati in scenari diversi. Una <xref:System.Windows.Controls.RichTextBox> è la scelta migliore quando è necessario che l'utente modifichi testo formattato, immagini, tabelle o altri contenuti avanzati. Ad esempio, la modifica di un documento, di un articolo o di un blog che richiede la formattazione, le immagini e così via viene eseguita con maggiore utilizzo <xref:System.Windows.Controls.RichTextBox> . Un oggetto <xref:System.Windows.Controls.TextBox> richiede un minor numero di risorse di sistema, un oggetto <xref:System.Windows.Controls.RichTextBox> ed è ideale quando è necessario modificare solo testo normale, ad esempio l'utilizzo nei moduli. Per ulteriori informazioni su, vedere [Cenni preliminari sulla casella di testo](textbox-overview.md) <xref:System.Windows.Controls.TextBox> . Nella tabella seguente sono riepilogate le principali funzionalità di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> .

|Controllo|Controllo ortografico in tempo reale|Menu di scelta rapida|Formattazione di comandi come <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument>contenuto come immagini, paragrafi, tabelle e così via.|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|sì|Sì|No|No.|
|<xref:System.Windows.Controls.RichTextBox>|sì|sì|sì|Sì|

> [!NOTE]
> Sebbene non <xref:System.Windows.Controls.TextBox> supporti i comandi correlati alla formattazione come <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B), molti comandi di base sono supportati da entrambi i controlli, ad esempio <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> .

Le funzionalità della tabella precedente vengono illustrate in dettaglio più avanti.

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a>Creazione di un oggetto RichTextBox

Il codice seguente illustra come creare un oggetto <xref:System.Windows.Controls.RichTextBox> che può essere modificato da un utente in.

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

In particolare, il contenuto modificato in un <xref:System.Windows.Controls.RichTextBox> è il contenuto del flusso. Tale contenuto può includere molti tipi di elementi, ad esempio testo formattato, immagini, elenchi e tabelle. Per informazioni approfondite sui documenti dinamici, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md). Per contenere il contenuto del flusso, un <xref:System.Windows.Controls.RichTextBox> oggetto ospita un <xref:System.Windows.Documents.FlowDocument> oggetto che a sua volta contiene il contenuto modificabile. Per illustrare il contenuto del flusso in un oggetto <xref:System.Windows.Controls.RichTextBox> , il codice seguente illustra come creare un oggetto <xref:System.Windows.Controls.RichTextBox> con un paragrafo e un testo in grassetto.

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

La figura seguente illustra come viene eseguito il rendering dell'esempio.

![RichTextBox con contenuto](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")

Elementi come <xref:System.Windows.Documents.Paragraph> e <xref:System.Windows.Documents.Bold> determinano il modo in cui viene visualizzato il contenuto all'interno di <xref:System.Windows.Controls.RichTextBox> . Quando un utente modifica <xref:System.Windows.Controls.RichTextBox> il contenuto, modifica il contenuto del flusso. Per altre informazioni sulle funzionalità del contenuto di flusso e sul relativo uso, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md).

> [!NOTE]
> Il contenuto del flusso all'interno di un <xref:System.Windows.Controls.RichTextBox> non si comporta esattamente come il contenuto del flusso contenuto in altri controlli. Ad esempio, non sono presenti colonne in un oggetto <xref:System.Windows.Controls.RichTextBox> e pertanto nessun comportamento di ridimensionamento automatico. Inoltre, le funzionalità predefinite come la ricerca, la modalità di visualizzazione, la navigazione tra le pagine e lo zoom non sono disponibili in un <xref:System.Windows.Controls.RichTextBox> .

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a>Controllo ortografico in tempo reale

È possibile abilitare il controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> . Quando il controllo ortografico è attivato, viene visualizzata una riga rossa sotto le parole errate (vedere la figura seguente).

![TextBox con controllo ortografico&#45;](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")

Per informazioni su come abilitare il controllo ortografico, vedere [Procedura: attivare il controllo ortografico in un controllo di modifica del testo](how-to-enable-spell-checking-in-a-text-editing-control.md).

<a name="context_menu"></a>

## <a name="context-menu"></a>Menu di scelta rapida

Per impostazione predefinita, <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> dispongono di un menu di scelta rapida che viene visualizzato quando un utente fa clic con il pulsante destro del mouse all'interno del controllo. Il menu di scelta rapida consente all'utente di eseguire operazioni di Taglia, Copia o Incolla (vedere la figura seguente).

![TextBox con menu di scelta rapida](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")

È possibile creare un menu di scelta rapida personalizzato per ignorare quello predefinito. Per altre informazioni, vedere [ Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md).

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a>Comandi di modifica

La modifica di comandi consente agli utenti di formattare contenuto modificabile all'interno di un <xref:System.Windows.Controls.RichTextBox> . Oltre ai comandi di modifica <xref:System.Windows.Controls.RichTextBox> di base, include i comandi di formattazione che <xref:System.Windows.Controls.TextBox> non supportano. Ad esempio, quando si modifica in un <xref:System.Windows.Controls.RichTextBox> , un utente può premere Ctr + B per impostare la formattazione del testo in grassetto. <xref:System.Windows.Documents.EditingCommands>Per un elenco completo dei comandi disponibili, vedere. Oltre a usare i tasti di scelta rapida, è possibile associare i comandi ad altri controlli, quali i pulsanti. L'esempio seguente illustra la procedura per creare una barra degli strumenti semplice, che l'utente potrà usare per modificare la formattazione del testo.

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

La figura seguente illustra la visualizzazione dell'esempio.

![RichTextBox con ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a>Rilevare le modifiche di contenuto

In genere <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> , l'evento deve essere usato per rilevare ogni volta che il testo in un oggetto <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> viene modificato piuttosto che <xref:System.Windows.UIElement.KeyDown> come previsto. Per un esempio, vedere [Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a>Salvare, caricare e stampare il contenuto di RichTextBox

Nell'esempio seguente viene illustrato come salvare il contenuto di un oggetto in <xref:System.Windows.Controls.RichTextBox> un file, caricare nuovamente il contenuto in <xref:System.Windows.Controls.RichTextBox> e stampare il contenuto. Di seguito è indicato il markup per l'esempio.

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

Di seguito è indicato il code-behind per l'esempio.

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a>Vedere anche

- [Procedure relative](richtextbox-how-to-topics.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
