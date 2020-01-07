---
title: Cenni preliminari sulle annotazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: b82c7e7300ebc295ca06d565c2fb5f6f2b28e92c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636510"
---
# <a name="annotations-overview"></a>Cenni preliminari sulle annotazioni
La scrittura di note o commenti su documenti cartacei è un'attività comune che diamo quasi per scontata. Queste note o commenti sono "annotazioni" aggiunte a un documento per contrassegnare informazioni o evidenziare elementi di interesse a cui fare riferimento in un secondo momento. Sebbene la scrittura di note su documenti stampati sia un'operazione semplice e comune, la capacità di aggiungere commenti personali ai documenti elettronici, se disponibile, è in genere molto limitata.  
  
 In questo argomento vengono esaminati diversi tipi comuni di annotazioni, in particolare note e evidenziazioni e viene illustrato il modo in cui il framework delle annotazioni Microsoft semplifica questi tipi di annotazioni nelle applicazioni tramite il Windows Presentation Foundation (WPF ) controlli di visualizzazione del documento.  I controlli di visualizzazione dei documenti WPF che supportano le annotazioni includono <xref:System.Windows.Controls.FlowDocumentReader> e <xref:System.Windows.Controls.FlowDocumentScrollViewer>, nonché controlli derivati da <xref:System.Windows.Controls.Primitives.DocumentViewerBase> come <xref:System.Windows.Controls.DocumentViewer> e <xref:System.Windows.Controls.FlowDocumentPageViewer>.  

<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a>Memo  
 Normalmente una nota adesiva contiene informazioni scritte su un pezzetto di carta colorata che viene successivamente "attaccato" su un documento. Le note adesive digitali forniscono funzionalità simili per i documenti elettronici, ma con la flessibilità aggiuntiva per includere molti altri tipi di contenuto, ad esempio il testo tipizzato, le note scritte a mano (ad esempio, i tratti di "input penna" di Tablet PC) o i collegamenti Web.  
  
 La figura seguente mostra alcuni esempi di annotazioni con evidenziatore, annotazioni di testo con Memo e annotazioni a penna di Memo.  
  
 ![Evidenziazioni, testo e annotazioni Sticky Note input penna.](./media/caf-stickynote.jpg "CAF_StickyNote")  
  
 L'esempio seguente illustra il metodo che è possibile usare per abilitare il supporto delle annotazioni nell'applicazione.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a>Evidenziazioni  
 Quando si eseguono annotazioni su un documento cartaceo, per attirare l'attenzione su elementi di interesse si usano metodi creativi, ad esempio sottolineando, evidenziando, cerchiando parole in una frase o tracciando segni o notazioni sul margine.  Le annotazioni evidenziate in Microsoft Annotations Framework forniscono una funzionalità simile per contrassegnare le informazioni visualizzate nei controlli di visualizzazione dei documenti WPF.  
  
 La figura seguente mostra un esempio di annotazione con evidenziatore.  
  
 ![Evidenzia annotazione](./media/caf-callouts.png "CAF_Callouts")  
  
 Gli utenti in genere creano annotazioni selezionando prima di tutto un testo o un elemento di interesse, quindi facendo clic con il pulsante destro del mouse per visualizzare un <xref:System.Windows.Controls.ContextMenu> di opzioni di annotazione.  Nell'esempio seguente viene illustrata la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare per dichiarare una <xref:System.Windows.Controls.ContextMenu> con i comandi indirizzati a cui gli utenti possono accedere per creare e gestire le annotazioni.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a>Ancoraggio dei dati  
 Il framework delle annotazioni associa le annotazioni ai dati selezionati dall'utente, non solo a una posizione nella visualizzazione. Pertanto, se la visualizzazione del documento cambia, ad esempio quando l'utente scorre o ridimensiona la finestra di visualizzazione, l'annotazione rimane nella selezione dati alla quale è associata. Ad esempio, l'immagine seguente mostra un'annotazione effettuata dall'utente su una selezione di testo. Quando la visualizzazione del documento cambia (scorre, viene ridimensionata o si sposta), l'annotazione con evidenziatore si sposta insieme alla selezione dati originale.  
  
 ![Ancoraggio dati annotazione](./media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a>Abbinamento delle annotazioni agli oggetti con annotazioni  
 È possibile abbinare le annotazioni agli oggetti con annotazioni corrispondenti. Si consideri, ad esempio, una semplice applicazione per la lettura di documenti con un riquadro dei commenti. Il riquadro dei commenti potrebbe essere una casella di riepilogo in cui viene visualizzato il testo di un elenco di annotazioni ancorate a un documento. Se l'utente seleziona un elemento della casella di riepilogo, nell'applicazione viene visualizzato il paragrafo del documento a cui è ancorato l'oggetto di annotazione corrispondente.  
  
 L'esempio seguente dimostra come implementare il gestore eventi di una casella di riepilogo di questo tipo che funge da riquadro dei commenti.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Un altro scenario di esempio riguarda le applicazioni che consentono lo scambio di annotazioni e note permanenti tra i lettori di documenti tramite posta elettronica. Questa funzionalità consente a tali applicazioni di far spostare il lettore alla pagina contenente l'annotazione che viene scambiata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [Schema annotazioni](annotations-schema.md)
- [Panoramica sull'oggetto ContextMenu](../controls/contextmenu-overview.md)
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [How to: Add a Command to a MenuItem (Procedura: Aggiungere un comando a un MenuItem)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
