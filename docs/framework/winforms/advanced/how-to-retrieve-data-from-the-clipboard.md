---
title: 'Procedura: recuperare dati dagli Appunti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c009efe743865896341da268bd14bf24158df46d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Procedura: recuperare dati dagli Appunti
La <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile utilizzare per interagire con la funzionalità degli Appunti di sistema operativo Windows. Molte applicazioni utilizzano negli Appunti come archivio temporaneo per i dati. Elaboratori di testo, ad esempio, usare gli Appunti durante le operazioni di taglia e Incolla. Sono utili per il trasferimento di informazioni da un'applicazione a altra anche negli Appunti.  
  
 Alcune applicazioni di archiviano i dati negli Appunti in più formati per aumentare il numero di altre applicazioni che possono utilizzare i dati. Un formato degli Appunti è una stringa che identifica il formato. Un'applicazione che utilizza tale formato è possibile recuperare i dati associati negli Appunti. La <xref:System.Windows.Forms.DataFormats> classe fornisce i nomi di formato predefinito per l'uso. È inoltre possibile utilizzare nomi di formato personalizzati o utilizzare un tipo di oggetto come formato. Per informazioni sull'aggiunta di dati negli Appunti, vedere [procedura: aggiungere dati negli Appunti](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Per determinare se gli Appunti contengono dati in un formato specifico, utilizzare uno del `Contains` *formato* metodi o <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo. Per recuperare dati dagli Appunti, utilizzare uno del `Get` *formato* metodi o <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo. Questi metodi sono nuovi in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Per accedere ai dati dagli Appunti con le versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], utilizzare il <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> (metodo) e chiamare i metodi dell'oggetto restituito <xref:System.Windows.Forms.IDataObject>. Per determinare se un particolare formato è disponibile nell'oggetto restituito, ad esempio, chiamare il <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> metodo.  
  
> [!NOTE]
>  Tutte le applicazioni basate su Windows condividono gli Appunti di sistema. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.  
>   
>  La <xref:System.Windows.Forms.Clipboard> classe può essere utilizzata solo nei thread impostati sulla modalità single thread apartment (STA). Per utilizzare questa classe, assicurarsi che il `Main` metodo è contrassegnato con il <xref:System.STAThreadAttribute> attributo.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Per recuperare i dati dagli Appunti in un formato comune  
  
1.  Utilizzare il <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> metodo. Facoltativamente, utilizzare la corrispondente `Contains` *formato* metodi per determinare se i dati sono disponibili in un formato specifico. Questi metodi sono disponibili solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Per recuperare i dati dagli Appunti in un formato personalizzato  
  
1.  Utilizzare il <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo con un nome di formato personalizzata. Questo metodo è disponibile solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     È inoltre possibile utilizzare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo. Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Per recuperare i dati dagli Appunti in più formati  
  
1.  Usare il metodo <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. È necessario utilizzare questo metodo per recuperare i dati dagli Appunti nelle versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche  
 [Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)  
 [Procedura: Aggiungere dati agli Appunti](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
