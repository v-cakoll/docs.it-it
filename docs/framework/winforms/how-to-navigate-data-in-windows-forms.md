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
ms.openlocfilehash: eb973497f51592b5d34c22e62da77612aec23c35
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964281"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Procedura: Esplorare dati in Windows Forms
In un'applicazione Windows il modo più semplice per spostarsi tra i record in un'origine dati consiste nell'associare <xref:System.Windows.Forms.BindingSource> un componente all'origine dati e quindi associare i <xref:System.Windows.Forms.BindingSource>controlli a. È quindi possibile usare il metodo di navigazione <xref:System.Windows.Forms.BindingSource> incorporato su <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> e <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Utilizzando questi metodi, le <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà e <xref:System.Windows.Forms.BindingSource.Current%2A> di <xref:System.Windows.Forms.BindingSource> vengono modificate in modo appropriato. È inoltre possibile trovare un elemento e impostarlo come elemento corrente impostando la <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Per incrementare la posizione in un'origine dati  
  
1. Impostare la <xref:System.Windows.Forms.BindingSource.Position%2A> proprietà <xref:System.Windows.Forms.BindingSource> del per i dati associati sulla posizione del record a cui passare. Nell'esempio seguente viene illustrato l'utilizzo <xref:System.Windows.Forms.BindingSource.MoveNext%2A> del metodo <xref:System.Windows.Forms.BindingSource> di per `nextButton` incrementare <xref:System.Windows.Forms.BindingSource.Position%2A> la proprietà quando si fa clic su. L' <xref:System.Windows.Forms.BindingSource> oggetto è associato `Customers` alla tabella di un set `Northwind`di dati.  
  
    > [!NOTE]
    > Se si <xref:System.Windows.Forms.BindingSource.Position%2A> imposta la proprietà su un valore oltre il primo o l'ultimo record, non viene generato un errore, poiché il .NET Framework non consentirà di impostare la posizione su un valore non compreso nei limiti dell'elenco. Se è importante per l'applicazione sapere se è stato superato il primo o l'ultimo record, includere la logica per verificare se il numero di elementi dati verrà superato.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Per verificare se è stata superata la fine o l'inizio  
  
1. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. Nel gestore è possibile verificare se il valore di posizione proposto ha superato il numero di elementi dati effettivi.  
  
     Nell'esempio seguente viene illustrato come è possibile verificare se è stato raggiunto l'ultimo elemento dati. Nell'esempio, se si è in corrispondenza dell'ultimo elemento, il pulsante **Avanti** nel form è disabilitato.  
  
    > [!NOTE]
    > Tenere presente che, se si modifica l'elenco che si sta spostando nel codice, è necessario riabilitare il pulsante **Avanti** , in modo che gli utenti possano sfogliare l'intera lunghezza del nuovo elenco. Tenere inoltre presente che l'evento precedente <xref:System.Windows.Forms.BindingSource.PositionChanged> per l'oggetto specifico <xref:System.Windows.Forms.BindingSource> che si sta utilizzando deve essere associato al relativo metodo di gestione degli eventi. Di seguito è riportato un esempio di un metodo per la <xref:System.Windows.Forms.BindingSource.PositionChanged> gestione dell'evento:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Per trovare un elemento e impostarlo come elemento corrente  
  
1. Trovare il record che si desidera impostare come elemento corrente. Questa operazione può essere eseguita usando <xref:System.Windows.Forms.BindingSource.Find%2A> il metodo <xref:System.Windows.Forms.BindingSource>di, se l'origine dati implementa <xref:System.ComponentModel.IBindingList>. Alcuni esempi di origini dati che <xref:System.ComponentModel.IBindingList> implementano <xref:System.ComponentModel.BindingList%601> sono <xref:System.Data.DataView>e.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Origini dati supportate da Windows Form](data-sources-supported-by-windows-forms.md)
- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
