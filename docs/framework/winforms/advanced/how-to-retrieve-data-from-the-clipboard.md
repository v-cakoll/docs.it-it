---
title: 'Procedura: Recuperare dati dagli Appunti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: e8f77a4fd1047598d51c2e0932d9c1309a305a86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003925"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Procedura: Recuperare dati dagli Appunti
Il <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile usare per interagire con la funzionalità degli Appunti di sistema operativo Windows. Molte applicazioni usano negli Appunti come un archivio temporaneo per i dati. Elaboratori di testo, ad esempio, usare gli Appunti durante le operazioni di taglia e Incolla. Gli Appunti sono anche utili per il trasferimento di informazioni da un'applicazione a altra.  
  
 Alcune applicazioni di archiviano i dati negli Appunti in più formati per aumentare il numero di altre applicazioni che possono utilizzare i dati. Un formato degli Appunti è una stringa che identifica il formato. Un'applicazione che utilizza il formato identificato può recuperare i dati associati negli Appunti. Il <xref:System.Windows.Forms.DataFormats> classe fornisce i nomi di formato predefinito per l'uso. È anche possibile usare i propri nomi di formato o utilizzare un tipo di oggetto come formato. Per informazioni sull'aggiunta di dati negli Appunti, vedere [come: Aggiungere dati agli Appunti](how-to-add-data-to-the-clipboard.md).  
  
 Per determinare se gli Appunti contengono dati in un formato specifico, usare uno dei `Contains` *formato* metodi o <xref:System.Windows.Forms.Clipboard.GetData%2A> (metodo). Per recuperare dati dagli Appunti, usare uno dei `Get` *formato* metodi o <xref:System.Windows.Forms.Clipboard.GetData%2A> (metodo). Questi metodi sono una novità [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Per accedere ai dati dagli Appunti con le versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], usare il <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> metodo e chiama i metodi dell'oggetto restituito <xref:System.Windows.Forms.IDataObject>. Per determinare se un particolare formato è disponibile nell'oggetto restituito, ad esempio, chiamare il <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> (metodo).  
  
> [!NOTE]
>  Tutte le applicazioni basate su Windows condividono gli Appunti di sistema. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.  
>   
>  Il <xref:System.Windows.Forms.Clipboard> classe può essere utilizzata solo nel thread impostato su modalità single thread apartment (STA). Per usare questa classe, assicurarsi che il `Main` metodo è contrassegnato con il <xref:System.STAThreadAttribute> attributo.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Per recuperare i dati dagli Appunti in un formato comune  
  
1. Usare la <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> (metodo). Facoltativamente, usare la corrispondente `Contains` *formato* metodi per determinare se i dati sono disponibili in un formato particolare. Questi metodi sono disponibili solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Per recuperare i dati dagli Appunti in un formato personalizzato  
  
1. Usare il <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo con un nome di formato personalizzato. Questo metodo è disponibile solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     È anche possibile usare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> (metodo). Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Per recuperare i dati dagli Appunti in più formati  
  
1. Usare il metodo <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. È necessario utilizzare questo metodo per recuperare i dati dagli Appunti in versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
- [Procedura: Aggiungere dati agli Appunti](how-to-add-data-to-the-clipboard.md)
