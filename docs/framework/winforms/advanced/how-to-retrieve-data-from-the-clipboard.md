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
ms.openlocfilehash: 88c2f2d872ae32b2cb3f0df13ce4816400695385
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963777"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Procedura: Recuperare dati dagli Appunti
La <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile usare per interagire con la funzionalità degli Appunti del sistema operativo Windows. Molte applicazioni usano gli Appunti come repository temporaneo per i dati. Ad esempio, i processori di Word usano gli appunti durante le operazioni di taglia e incolla. Gli Appunti sono utili anche per trasferire le informazioni da un'applicazione a un'altra.  
  
 Alcune applicazioni archiviano i dati negli Appunti in più formati per aumentare il numero di altre applicazioni che possono potenzialmente utilizzare i dati. Un formato degli Appunti è una stringa che identifica il formato. Un'applicazione che utilizza il formato identificato può recuperare i dati associati negli Appunti. La <xref:System.Windows.Forms.DataFormats> classe fornisce nomi di formato predefiniti per l'utilizzo. È anche possibile usare nomi di formato personalizzati o usare il tipo di un oggetto come formato. Per informazioni sull'aggiunta di dati negli Appunti, vedere [procedura: Aggiungere i dati negli Appunti](how-to-add-data-to-the-clipboard.md).  
  
 Per determinare se gli Appunti contengono dati in un formato particolare, usare uno dei metodi `Contains`di *formattazione* o il <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo. Per recuperare i dati dagli Appunti, usare uno dei metodi `Get`di *formattazione* o il <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo. Questi metodi sono una novità di .NET Framework 2,0.  
  
 Per accedere ai dati dagli Appunti utilizzando versioni precedenti a .NET Framework 2,0, utilizzare il <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> metodo e chiamare i metodi dell'oggetto restituito. <xref:System.Windows.Forms.IDataObject> Per determinare se un particolare formato è disponibile nell'oggetto restituito, ad esempio, chiamare il <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> metodo.  
  
> [!NOTE]
> Tutte le applicazioni basate su Windows condividono gli Appunti di sistema. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.  
>   
>  La <xref:System.Windows.Forms.Clipboard> classe può essere usata solo nei thread impostati sulla modalità Apartment a thread singolo (sta). Per usare questa classe, verificare che il `Main` metodo sia contrassegnato con l' <xref:System.STAThreadAttribute> attributo.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Per recuperare i dati dagli Appunti in un unico formato comune  
  
1. Usare il <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>metodo <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> . Facoltativamente, usare prima i `Contains`metodi di *formattazione* corrispondenti per determinare se i dati sono disponibili in un particolare formato. Questi metodi sono disponibili solo in .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Per recuperare i dati dagli Appunti in un formato personalizzato  
  
1. Usare il <xref:System.Windows.Forms.Clipboard.GetData%2A> metodo con un nome di formato personalizzato. Questo metodo è disponibile solo in .NET Framework 2,0.  
  
     È anche possibile usare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo. Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Per recuperare i dati dagli Appunti in più formati  
  
1. Usare il metodo <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. È necessario utilizzare questo metodo per recuperare i dati dagli Appunti nelle versioni precedenti a .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
- [Procedura: Aggiungere dati agli Appunti](how-to-add-data-to-the-clipboard.md)
