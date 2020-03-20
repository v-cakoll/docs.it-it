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
ms.openlocfilehash: 433fee08d44720640d3f9d1bf2511a6a267eb58e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145462"
---
# <a name="annotations-overview"></a>Cenni preliminari sulle annotazioni
La scrittura di note o commenti su documenti cartacei è un'attività comune che diamo quasi per scontata. Queste note o commenti sono "annotazioni" aggiunte a un documento per contrassegnare informazioni o evidenziare elementi di interesse a cui fare riferimento in un secondo momento. Sebbene la scrittura di note su documenti stampati sia un'operazione semplice e comune, la capacità di aggiungere commenti personali ai documenti elettronici, se disponibile, è in genere molto limitata.  
  
 In questo argomento vengono esaminati diversi tipi comuni di annotazioni, in particolare note e evidenziazioni, e viene illustrato come Microsoft Annotations Framework facilita questi tipi di annotazioni nelle applicazioni tramite Windows Presentation Foundation (WPF) ) controlli di visualizzazione dei documenti.  I controlli di visualizzazione dei <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentScrollViewer>documenti WPFWPF che <xref:System.Windows.Controls.Primitives.DocumentViewerBase> supportano <xref:System.Windows.Controls.DocumentViewer> <xref:System.Windows.Controls.FlowDocumentPageViewer>le annotazioni includono e , nonché i controlli derivati da quali, e .  

<a name="caf1_type_stickynotes"></a>
## <a name="sticky-notes"></a>Memo  
 Normalmente una nota adesiva contiene informazioni scritte su un pezzetto di carta colorata che viene successivamente "attaccato" su un documento. Le note adesive digitali forniscono funzionalità simili per i documenti elettronici, ma con la flessibilità aggiuntiva di includere molti altri tipi di contenuto, ad esempio testo digitato, note scritte a mano (ad esempio, tratti "input penna" di Tablet PC) o collegamenti Web.  
  
 La figura seguente mostra alcuni esempi di annotazioni con evidenziatore, annotazioni di testo con Memo e annotazioni a penna di Memo.  
  
 ![Annotazioni con evidenziatore, testo e a penna Sticky Notes](./media/caf-stickynote.jpg "CAF_StickyNote")  
  
 L'esempio seguente illustra il metodo che è possibile usare per abilitare il supporto delle annotazioni nell'applicazione.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>
## <a name="highlights"></a>In evidenza  
 Quando si eseguono annotazioni su un documento cartaceo, per attirare l'attenzione su elementi di interesse si usano metodi creativi, ad esempio sottolineando, evidenziando, cerchiando parole in una frase o tracciando segni o notazioni sul margine.  Evidenziare le annotazioni in Microsoft Annotations Framework forniscono una funzionalità simile per contrassegnare le informazioni visualizzate nei controlli di visualizzazione dei documenti WPFWPF.  
  
 La figura seguente mostra un esempio di annotazione con evidenziatore.  
  
 ![Annotazione con evidenziatore](./media/caf-callouts.png "CAF_Callouts")  
  
 Gli utenti in genere creano annotazioni selezionando prima del testo o un <xref:System.Windows.Controls.ContextMenu> elemento di interesse e quindi facendo clic con il pulsante destro del mouse per visualizzare una delle opzioni di annotazione.  Nell'esempio seguente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] viene illustrato l'è possibile utilizzare per dichiarare un <xref:System.Windows.Controls.ContextMenu> con i comandi indirizzati a cui gli utenti possono accedere per creare e gestire le annotazioni.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>
## <a name="data-anchoring"></a>Ancoraggio dei dati  
 Annotations Framework associa le annotazioni ai dati selezionati dall'utente, non solo a una posizione nella visualizzazione di visualizzazione. Pertanto, se la visualizzazione del documento cambia, ad esempio quando l'utente scorre o ridimensiona la finestra di visualizzazione, l'annotazione rimane nella selezione dati alla quale è associata. Ad esempio, l'immagine seguente mostra un'annotazione effettuata dall'utente su una selezione di testo. Quando la visualizzazione del documento cambia (scorre, viene ridimensionata o si sposta), l'annotazione con evidenziatore si sposta insieme alla selezione dati originale.  
  
 ![Ancoraggio dei dati dell'annotazione](./media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>
## <a name="matching-annotations-with-annotated-objects"></a>Abbinamento delle annotazioni agli oggetti con annotazioni  
 È possibile abbinare le annotazioni agli oggetti con annotazioni corrispondenti. Si consideri, ad esempio, una semplice applicazione per la lettura di documenti con un riquadro dei commenti. Il riquadro dei commenti potrebbe essere una casella di riepilogo in cui viene visualizzato il testo di un elenco di annotazioni ancorate a un documento. Se l'utente seleziona un elemento della casella di riepilogo, nell'applicazione viene visualizzato il paragrafo del documento a cui è ancorato l'oggetto di annotazione corrispondente.  
  
 L'esempio seguente dimostra come implementare il gestore eventi di una casella di riepilogo di questo tipo che funge da riquadro dei commenti.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Un altro scenario di esempio prevede applicazioni che consentono lo scambio di annotazioni e note adesive tra i lettori di documenti tramite posta elettronica. Questa funzionalità consente a tali applicazioni di far spostare il lettore alla pagina contenente l'annotazione che viene scambiata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [Schema annotazioni](annotations-schema.md)
- [Panoramica sull'oggetto ContextMenu](../controls/contextmenu-overview.md)
- [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md)
- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [How to: Add a Command to a MenuItem (Procedura: Aggiungere un comando a un MenuItem)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
