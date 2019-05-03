---
title: 'Procedura: Esplorare dati in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2ba33f9ecb3a12a62c41af17d3f9ad6f6e3f8a5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801712"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Procedura: Esplorare dati in Windows Forms
In un'applicazione di Windows, è il modo più semplice per spostarsi tra i record in un'origine dati per associare un <xref:System.Windows.Forms.BindingSource> componente per l'origine dati e quindi associare i controlli per il <xref:System.Windows.Forms.BindingSource>. È quindi possibile utilizzare il metodo di navigazione predefiniti in di <xref:System.Windows.Forms.BindingSource> tali una <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> e <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Usando questi metodi regolerà la <xref:System.Windows.Forms.BindingSource.Position%2A> e <xref:System.Windows.Forms.BindingSource.Current%2A> delle proprietà del <xref:System.Windows.Forms.BindingSource> in modo appropriato. È anche possibile trovare un elemento e impostarlo come elemento corrente, impostando il <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Per incrementare la posizione in un'origine dati  
  
1. Impostare il <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà del <xref:System.Windows.Forms.BindingSource> per i dati associati alla posizione del record su cui spostarsi. Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Forms.BindingSource.MoveNext%2A> metodo del <xref:System.Windows.Forms.BindingSource> per incrementare il <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà quando il `nextButton` si fa clic. Il <xref:System.Windows.Forms.BindingSource> è associato il `Customers` tabella di un set di dati `Northwind`.  
  
    > [!NOTE]
    >  Impostando il <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà su un valore di là del primo o ultimo record non produce un errore, come il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non consentirà di impostare la posizione su un valore esterno ai limiti dell'elenco. Se è importante per sapere se è stato oltrepassato il primo o ultimo record in un'applicazione, includere la logica per verificare se si supera il numero di elementi di dati.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Per verificare se sono stati passati alla fine o all'inizio  
  
1. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. Nel gestore di è possibile verificare se il valore di posizione proposto ha superato il numero di elementi di dati effettivi.  
  
     Nell'esempio seguente viene illustrato come è possibile verificare se è stato raggiunto l'ultimo elemento di dati. Nell'esempio, se ci si trova l'ultimo elemento, il **successivo** pulsante nel form è disabilitato.  
  
    > [!NOTE]
    >  Tenere presente che, se si modifica l'elenco di navigazione nel codice, è necessario attivare nuovamente il **successivo** pulsante, in modo che gli utenti possono visualizzare l'intera durata del nuovo elenco. Inoltre, tenere presente che il codice precedente <xref:System.Windows.Forms.BindingSource.PositionChanged> eventi per lo specifico <xref:System.Windows.Forms.BindingSource> si lavora con deve essere associato al relativo metodo di gestione degli eventi. Di seguito è riportato un esempio di un metodo per la gestione di <xref:System.Windows.Forms.BindingSource.PositionChanged> evento:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Per trovare un elemento e impostarlo come elemento corrente  
  
1. Trovare il record che si desidera impostare come elemento corrente. È possibile farlo usando il <xref:System.Windows.Forms.BindingSource.Find%2A> metodo per il <xref:System.Windows.Forms.BindingSource>, se l'origine dati implementa <xref:System.ComponentModel.IBindingList>. Alcuni esempi di dati di origini che implementano <xref:System.ComponentModel.IBindingList> vengono <xref:System.ComponentModel.BindingList%601> e <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Origini dati supportate da Windows Form](data-sources-supported-by-windows-forms.md)
- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
