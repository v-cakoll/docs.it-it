---
title: 'Procedura: Aggiungere dati agli Appunti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 03d3a0c6026761fcdbc45472f2bbb7ac593f4394
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325683"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Procedura: Aggiungere dati agli Appunti
Il <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile usare per interagire con la funzionalità degli Appunti di sistema operativo Windows. Molte applicazioni usano negli Appunti come un archivio temporaneo per i dati. Elaboratori di testo, ad esempio, usare gli Appunti durante le operazioni di taglia e Incolla. Gli Appunti sono anche utili per il trasferimento dei dati da un'applicazione a altra.  
  
 Quando si aggiungono dati negli Appunti, è possibile indicare il formato dei dati in modo che altre applicazioni in grado di riconoscere i dati se è possibile utilizzare tale formato. È anche possibile aggiungere i dati negli Appunti in più formati diversi per aumentare il numero di altre applicazioni che possono utilizzare i dati.  
  
 Un formato degli Appunti è una stringa che identifica il formato in modo che un'applicazione che usa questo formato può recuperare i dati associati. Il <xref:System.Windows.Forms.DataFormats> classe fornisce i nomi di formato predefinito per l'uso. È anche possibile usare nomi di formato personalizzati o usare il tipo di un oggetto come relativo formato.  
  
 Per aggiungere i dati negli Appunti in uno o più formati, usare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> (metodo). È possibile passare qualsiasi oggetto a questo metodo, ma per aggiungere dati in più formati, è necessario aggiungere prima di tutto i dati a un oggetto separato progettato per funzionare con più formati. In genere, si aggiungerà i dati in un <xref:System.Windows.Forms.DataObject>, ma è possibile usare qualsiasi tipo che implementa il <xref:System.Windows.Forms.IDataObject> interfaccia.  
  
 In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], è possibile aggiungere i dati direttamente negli Appunti con nuovi metodi progettati per semplificare le attività di base negli Appunti. Usare questi metodi quando si lavora con i dati in un formato comune come testo.  
  
> [!NOTE]
>  Tutte le applicazioni basate su Windows condivideranno gli Appunti. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.  
>   
>  Il <xref:System.Windows.Forms.Clipboard> classe può essere utilizzata solo nel thread impostato su modalità single thread apartment (STA). Per usare questa classe, assicurarsi che il `Main` metodo è contrassegnato con il <xref:System.STAThreadAttribute> attributo.  
>   
>  Un oggetto deve essere serializzabile per poter essere inserita negli Appunti. Per rendere un tipo serializzabile, contrassegnarla con il <xref:System.SerializableAttribute> attributo. Se si passa un oggetto non serializzabile da un metodo negli Appunti, il metodo avrà esito negativo senza generare un'eccezione. Per altre informazioni sulla serializzazione, vedere <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Per aggiungere i dati negli Appunti in un formato comune  
  
1. Usare la <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> (metodo). Questi metodi sono disponibili solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Per aggiungere i dati negli Appunti in un formato personalizzato  
  
1. Usare il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo con un nome di formato personalizzato. Questo metodo è disponibile solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     È anche possibile usare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> (metodo). Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Per aggiungere i dati negli Appunti in più formati  
  
1. Usare la <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metodo e passare un <xref:System.Windows.Forms.DataObject> che contiene i dati. È necessario utilizzare questo metodo per aggiungere dati agli Appunti nelle versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Supporto delle operazioni di trascinamento della selezione e degli Appunti](drag-and-drop-operations-and-clipboard-support.md)
- [Procedura: Recuperare dati dagli Appunti](how-to-retrieve-data-from-the-clipboard.md)
