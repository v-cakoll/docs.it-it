---
title: 'Procedura: Aprire un file rilasciato in un controllo RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 8ffa4c9919788060dc4524e127c181ee8282e6f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768602"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Procedura: Aprire un file rilasciato in un controllo RichTextBox
Nelle [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], il <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> tutti i controlli dispongono di funzionalità di trascinamento e rilascio incorporate. La funzionalità incorporata consente di trascinamento e rilascio del testo all'interno e tra i controlli. Tuttavia, non abilita l'apertura di un file eliminando il file nel controllo. Questi controlli inoltre contrassegnano gli eventi di trascinamento e rilascio come gestito. Di conseguenza, per impostazione predefinita, è possibile aggiungere i propri gestori eventi per fornire la funzionalità di apertura file rilasciati.  
  
 Per aggiungere ulteriori operazioni di gestione per gli eventi di trascinamento e rilascio in questi controlli, usare il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metodo per aggiungere i gestori eventi per gli eventi di trascinamento e rilascio. Impostare il `handledEventsToo` parametro per `true` affinché il gestore specificato da richiamare per un evento indirizzato che è già stato contrassegnato come gestito da un altro elemento lungo la route dell'evento.  
  
> [!TIP]
>  È possibile sostituire la funzionalità di trascinamento e rilascio incorporata del <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> gestendo le versioni di anteprima degli eventi di trascinamento e rilascio e contrassegnare gli eventi di anteprima come gestito. Tuttavia, questo verrà disattivata la funzionalità di trascinamento e rilascio predefinita e non è consigliato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere i gestori per il <xref:System.Windows.DragDrop.DragOver> e <xref:System.Windows.DragDrop.Drop> eventi su un <xref:System.Windows.Controls.RichTextBox>. Questo esempio Usa il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> (metodo) e imposta il `handledEventsToo` parametro per `true` in modo che verranno richiamati anche se i gestori degli eventi il <xref:System.Windows.Controls.RichTextBox> contrassegna questi eventi come gestiti. Il codice nei gestori eventi aggiunge funzionalità che consente di aprire un file di testo che viene inserito nel <xref:System.Windows.Controls.RichTextBox>.  
  
 Per testare questo esempio, trascinare un file di testo o un file di formato (RTF) di testo RTF da Explorer di Windows per il <xref:System.Windows.Controls.RichTextBox>. Il file verrà aperto nel <xref:System.Windows.Controls.RichTextBox>. Se si preme il tasto MAIUSC prima di eliminare il file verrà aperto il file come testo normale.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
