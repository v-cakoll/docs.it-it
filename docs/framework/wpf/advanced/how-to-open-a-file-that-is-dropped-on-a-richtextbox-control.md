---
title: 'Procedura: aprire un file rilasciato in un controllo RichTextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dfb5f0f442b18159c18a6e5345f6757674fbb90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Procedura: aprire un file rilasciato in un controllo RichTextBox
In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> tutti i controlli sono incorporate funzionalità di trascinamento e rilascio. La funzionalità incorporata consente di trascinamento e rilascio del testo all'interno e tra i controlli. Tuttavia, non consente l'apertura di un file eliminando il file nel controllo. Questi controlli inoltre contrassegnano gli eventi di trascinamento e rilascio come gestito. Di conseguenza, per impostazione predefinita, è possibile aggiungere i propri gestori eventi per fornire la funzionalità di apertura file rilasciati.  
  
 Per aggiungere ulteriori operazioni di gestione per gli eventi di trascinamento e rilascio in questi controlli, utilizzare il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metodo per aggiungere i gestori eventi per gli eventi di trascinamento e rilascio. Impostare il `handledEventsToo` parametro `true` per il gestore specificato venga richiamato per un evento indirizzato è già stato contrassegnato come gestito da un altro elemento lungo la route dell'evento.  
  
> [!TIP]
>  È possibile sostituire la funzionalità di trascinamento e rilascio predefinita di <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Documents.FlowDocument> gestendo le versioni di anteprima degli eventi di trascinamento e rilascio e contrassegnare gli eventi di anteprima come gestito. Tuttavia, questo disabiliterà la funzionalità di trascinamento e rilascio predefinita e non è consigliato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere i gestori per il <xref:System.Windows.DragDrop.DragOver> e <xref:System.Windows.DragDrop.Drop> eventi su un <xref:System.Windows.Controls.RichTextBox>. Questo esempio viene utilizzato il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> (metodo) e imposta il `handledEventsToo` parametro `true` in modo che verranno richiamati anche se i gestori degli eventi il <xref:System.Windows.Controls.RichTextBox> contrassegna questi eventi come gestito. Il codice nei gestori di eventi consente di aprire un file di testo che viene eliminato il <xref:System.Windows.Controls.RichTextBox>.  
  
 Per testare questo esempio, trascinare un file di testo o un file di formato RTF RTF da Esplora risorse per il <xref:System.Windows.Controls.RichTextBox>. Il file verrà aperto nel <xref:System.Windows.Controls.RichTextBox>. Se si preme il tasto MAIUSC prima di eliminare il file, verrà aperto il file come testo normale.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
