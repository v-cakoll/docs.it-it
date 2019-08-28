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
ms.openlocfilehash: 0d9b82f01080d18353ecb91578a8005260bbe739
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044227"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Procedura: Aggiungere dati agli Appunti

La <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile usare per interagire con la funzionalità degli Appunti del sistema operativo Windows. Molte applicazioni usano gli Appunti come repository temporaneo per i dati. Ad esempio, i processori di Word usano gli appunti durante le operazioni di taglia e incolla. Gli Appunti sono utili anche per trasferire i dati da un'applicazione a un'altra.

Quando si aggiungono dati agli Appunti, è possibile indicare il formato dei dati in modo che le altre applicazioni possano riconoscere i dati se possono utilizzare tale formato. È anche possibile aggiungere dati agli Appunti in più formati diversi per aumentare il numero di altre applicazioni che potenzialmente possono usare i dati.

Un formato degli Appunti è una stringa che identifica il formato in modo che un'applicazione che utilizza tale formato possa recuperare i dati associati. La <xref:System.Windows.Forms.DataFormats> classe fornisce nomi di formato predefiniti per l'utilizzo. È anche possibile usare nomi di formato personalizzati o usare il tipo di un oggetto come formato.

Per aggiungere dati agli Appunti in uno o più formati, utilizzare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metodo. È possibile passare qualsiasi oggetto a questo metodo, ma per aggiungere dati in più formati è necessario innanzitutto aggiungere i dati a un oggetto separato progettato per funzionare con più formati. In genere, i dati vengono aggiunti a un <xref:System.Windows.Forms.DataObject>, ma è possibile usare qualsiasi tipo che implementi <xref:System.Windows.Forms.IDataObject> l'interfaccia.

In .NET Framework 2,0 è possibile aggiungere dati direttamente agli appunti usando nuovi metodi progettati per semplificare le attività di base degli Appunti. Usare questi metodi quando si lavora con i dati in un unico formato comune, ad esempio testo.

> [!NOTE]
> Tutte le applicazioni basate su Windows condividono gli Appunti. Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.
>
> La <xref:System.Windows.Forms.Clipboard> classe può essere usata solo nei thread impostati sulla modalità Apartment a thread singolo (sta). Per usare questa classe, verificare che il `Main` metodo sia contrassegnato con l' <xref:System.STAThreadAttribute> attributo.
>
> Un oggetto deve essere serializzabile affinché venga inserito negli Appunti. Per rendere un tipo serializzabile, contrassegnarlo con <xref:System.SerializableAttribute> l'attributo. Se si passa un oggetto non serializzabile a un metodo degli Appunti, il metodo avrà esito negativo senza generare un'eccezione. Per altre informazioni sulla serializzazione, vedere <xref:System.Runtime.Serialization>.

### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Per aggiungere dati agli Appunti in un unico formato comune

1. Usare il <xref:System.Windows.Forms.Clipboard.SetAudio%2A>metodo <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> . Questi metodi sono disponibili solo in .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Per aggiungere dati agli Appunti in un formato personalizzato

1. Usare il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo con un nome di formato personalizzato. Questo metodo è disponibile solo in .NET Framework 2,0.

    È anche possibile usare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo. Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Per aggiungere dati agli Appunti in più formati

1. Usare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> metodo e passare un oggetto <xref:System.Windows.Forms.DataObject> che contiene i dati. È necessario utilizzare questo metodo per aggiungere dati agli Appunti nelle versioni precedenti a .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>Vedere anche

- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
- [Procedura: Recuperare i dati dagli Appunti](how-to-retrieve-data-from-the-clipboard.md)
