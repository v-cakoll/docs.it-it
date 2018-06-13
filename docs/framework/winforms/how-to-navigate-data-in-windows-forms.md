---
title: 'Procedura: esplorare dati in Windows Form'
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
ms.openlocfilehash: 9572c1234c07c77d5df0c9cd58499faafe460e4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540368"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Procedura: esplorare dati in Windows Form
In un'applicazione Windows, il modo più semplice per spostarsi tra i record in un'origine dati è associare un <xref:System.Windows.Forms.BindingSource> componente per l'origine dati e quindi associare i controlli per il <xref:System.Windows.Forms.BindingSource>. È quindi possibile utilizzare il metodo di spostamento incorporate nel <xref:System.Windows.Forms.BindingSource> tali un <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> e <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Con questi metodi vengono adattate le <xref:System.Windows.Forms.BindingSource.Position%2A> e <xref:System.Windows.Forms.BindingSource.Current%2A> le proprietà del <xref:System.Windows.Forms.BindingSource> in modo appropriato. È inoltre possibile trovare un elemento e impostarlo come elemento corrente impostando la <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Per incrementare la posizione in un'origine dati  
  
1.  Impostare il <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà del <xref:System.Windows.Forms.BindingSource> per i dati associati alla posizione del record per passare a. Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Forms.BindingSource.MoveNext%2A> metodo del <xref:System.Windows.Forms.BindingSource> per incrementare la <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà quando il `nextButton` si fa clic. Il <xref:System.Windows.Forms.BindingSource> è associato il `Customers` tabella di un set di dati `Northwind`.  
  
    > [!NOTE]
    >  L'impostazione di <xref:System.Windows.Forms.BindingSource.Position%2A> un valore oltre il primo o ultimo record della proprietà non produce un errore, come il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non consente di impostare la posizione su un valore all'esterno dei limiti dell'elenco. Se è importante in un'applicazione per sapere se è stato oltrepassato il primo o ultimo record, includere la logica per verificare se viene superato il numero di elementi di dati.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Per verificare se sono stati passati alla fine o all'inizio  
  
1.  Creare un gestore eventi per l'evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. Nel gestore, è possibile verificare se il valore della posizione proposta ha superato il numero di elementi di dati effettivi.  
  
     Nell'esempio seguente viene illustrato come è possibile verificare se è stato raggiunto l'ultimo elemento di dati. Nell'esempio, se si sta utilizzando l'ultimo elemento, il **Avanti** pulsante nel form è disabilitato.  
  
    > [!NOTE]
    >  Tenere presente che, se si modifica l'elenco si sposta nel codice, è necessario attivare nuovamente il **Avanti** pulsante, in modo che gli utenti possono cercare l'intera durata del nuovo elenco. Inoltre, tenere presente che la precedente <xref:System.Windows.Forms.BindingSource.PositionChanged> evento per la specifica <xref:System.Windows.Forms.BindingSource> in uso deve essere associato con il metodo di gestione degli eventi. Di seguito è riportato un esempio di un metodo per la gestione di <xref:System.Windows.Forms.BindingSource.PositionChanged> evento:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Per trovare un elemento e impostarlo come elemento corrente  
  
1.  Trovare il record che si desidera impostare come elemento corrente. È possibile farlo usando il <xref:System.Windows.Forms.BindingSource.Find%2A> metodo il <xref:System.Windows.Forms.BindingSource>, se l'origine dati implementa <xref:System.ComponentModel.IBindingList>. Alcuni esempi di dati di origini che implementano <xref:System.ComponentModel.IBindingList> sono <xref:System.ComponentModel.BindingList%601> e <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Origini dati supportate da Windows Form](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
