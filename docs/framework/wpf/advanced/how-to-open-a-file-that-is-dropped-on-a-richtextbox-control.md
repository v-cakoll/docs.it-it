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
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046359"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Procedura: Aprire un file rilasciato in un controllo RichTextBox

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]i controlli <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> e<xref:System.Windows.Documents.FlowDocument> hanno tutti la funzionalità di trascinamento della selezione incorporata. La funzionalità incorporata consente il trascinamento della selezione del testo all'interno e tra i controlli. Tuttavia, non consente di aprire un file eliminando il file nel controllo. Questi controlli contrassegnano anche gli eventi di trascinamento della selezione come gestiti. Di conseguenza, per impostazione predefinita, non è possibile aggiungere gestori di eventi personalizzati per fornire funzionalità per aprire i file eliminati.

Per aggiungere la gestione aggiuntiva per gli eventi di trascinamento della selezione in questi <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> controlli, usare il metodo per aggiungere i gestori eventi per gli eventi di trascinamento della selezione. Impostare il `handledEventsToo` parametro su `true` per fare in modo che il gestore specificato venga richiamato per un evento indirizzato che è già stato contrassegnato come gestito da un altro elemento lungo la route dell'evento.

> [!TIP]
> È possibile sostituire la funzionalità di trascinamento della selezione predefinita di <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>e <xref:System.Windows.Documents.FlowDocument> gestendo le versioni di anteprima degli eventi di trascinamento della selezione e contrassegnando gli eventi di anteprima come gestiti. Tuttavia, questa operazione Disabilita la funzionalità di trascinamento della selezione incorporata e non è consigliata.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come aggiungere gestori per gli <xref:System.Windows.DragDrop.DragOver> eventi e <xref:System.Windows.DragDrop.Drop> in un oggetto. <xref:System.Windows.Controls.RichTextBox> Questo esempio usa il <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metodo e imposta il `handledEventsToo` parametro su `true` in modo che i <xref:System.Windows.Controls.RichTextBox> gestori eventi vengano richiamati anche se questi eventi vengono contrassegnati come gestiti. Il codice nei gestori eventi aggiunge funzionalità per aprire un file di testo rilasciato in <xref:System.Windows.Controls.RichTextBox>.

Per testare questo esempio, trascinare un file di testo o un file RTF (Rich Text Format) da Esplora risorse a <xref:System.Windows.Controls.RichTextBox>. Il file verrà aperto in <xref:System.Windows.Controls.RichTextBox>. Se si preme il tasto MAIUSC prima dell'eliminazione del file, il file verrà aperto come testo normale.

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
