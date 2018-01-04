---
title: 'Procedura: aggiungere dati agli Appunti'
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
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a>Procedura: aggiungere dati agli Appunti
La <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile utilizzare per interagire con la funzionalità degli Appunti di sistema operativo Windows. Molte applicazioni utilizzano negli Appunti come archivio temporaneo per i dati. Elaboratori di testo, ad esempio, usare gli Appunti durante le operazioni di taglia e Incolla. Sono utili per il trasferimento di dati da un'applicazione a altra anche negli Appunti.  
  
 Quando si aggiungono dati negli Appunti, è possibile indicare il formato dei dati in modo che le altre applicazioni possono riconoscere i dati se è possibile utilizzare tale formato. È anche possibile aggiungere dati negli Appunti in più formati diversi per aumentare il numero di altre applicazioni che possono utilizzare i dati.  
  
 Un formato degli Appunti è una stringa che identifica il formato in modo che un'applicazione che utilizza tale formato può recuperare i dati associati. La <xref:System.Windows.Forms.DataFormats> classe fornisce i nomi di formato predefinito per l'uso. È inoltre possibile utilizzare nomi di formato personalizzati o utilizzare il tipo di oggetto come formato.  
  
 Per aggiungere i dati negli Appunti in uno o più formati, utilizzare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metodo. È possibile passare qualsiasi oggetto a questo metodo, ma per aggiungere dati in più formati, è innanzitutto necessario aggiungere i dati per un oggetto separato, progettato per funzionare con più formati. In genere, si aggiungerà i dati in un <xref:System.Windows.Forms.DataObject>, ma è possibile utilizzare qualsiasi tipo che implementa il <xref:System.Windows.Forms.IDataObject> interfaccia.  
  
 In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], è possibile aggiungere dati direttamente negli Appunti utilizzando nuovi metodi progettati per semplificare le attività di base negli Appunti. Utilizzare questi metodi quando si lavora con dati in un formato comune, ad esempio testo.  
  
> [!NOTE]
>  Tutte le applicazioni basate su Windows condividono negli Appunti. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.  
>   
>  La <xref:System.Windows.Forms.Clipboard> classe può essere utilizzata solo nei thread impostati sulla modalità single thread apartment (STA). Per utilizzare questa classe, assicurarsi che il `Main` metodo è contrassegnato con il <xref:System.STAThreadAttribute> attributo.  
>   
>  Un oggetto deve essere serializzabile per poter essere inserito negli Appunti. Per rendere un tipo serializzabile, contrassegnarlo con il <xref:System.SerializableAttribute> attributo. Se si passa un oggetto non serializzabile a un metodo negli Appunti, il metodo avrà esito negativo senza generare un'eccezione. Per altre informazioni sulla serializzazione, vedere <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Per aggiungere i dati negli Appunti in un formato comune  
  
1.  Utilizzare il <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> metodo. Questi metodi sono disponibili solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Per aggiungere i dati negli Appunti in un formato personalizzato  
  
1.  Utilizzare il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo con un nome di formato personalizzata. Questo metodo è disponibile solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     È inoltre possibile utilizzare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo. Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Per aggiungere i dati negli Appunti in più formati  
  
1.  Utilizzare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> (metodo) e passare un <xref:System.Windows.Forms.DataObject> che contiene i dati. È necessario utilizzare questo metodo per aggiungere dati agli Appunti nelle versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche  
 [Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)  
 [Procedura: Recuperare dati dagli Appunti](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
