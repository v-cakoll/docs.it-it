---
title: 'Procedura: spostarsi tra i dati'
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
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739391"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Procedura: Esplorare dati in Windows Form
In un'applicazione Windows il modo più semplice per spostarsi tra i record in un'origine dati consiste nell'associare un componente <xref:System.Windows.Forms.BindingSource> all'origine dati e quindi associare i controlli al <xref:System.Windows.Forms.BindingSource>. È quindi possibile usare il metodo di navigazione incorporato sul <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> e <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. L'utilizzo di questi metodi modificherà il <xref:System.Windows.Forms.BindingSource.Position%2A> e <xref:System.Windows.Forms.BindingSource.Current%2A> proprietà del <xref:System.Windows.Forms.BindingSource> in modo appropriato. È inoltre possibile trovare un elemento e impostarlo come elemento corrente impostando la proprietà <xref:System.Windows.Forms.BindingSource.Position%2A>.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Per incrementare la posizione in un'origine dati  
  
1. Impostare la proprietà <xref:System.Windows.Forms.BindingSource.Position%2A> della <xref:System.Windows.Forms.BindingSource> per i dati associati sulla posizione del record a cui passare. Nell'esempio seguente viene illustrato l'utilizzo del metodo <xref:System.Windows.Forms.BindingSource.MoveNext%2A> della <xref:System.Windows.Forms.BindingSource> per incrementare la proprietà <xref:System.Windows.Forms.BindingSource.Position%2A> quando si fa clic sul `nextButton`. Il <xref:System.Windows.Forms.BindingSource> è associato alla tabella `Customers` di un set di dati `Northwind`.  
  
    > [!NOTE]
    > Se si imposta la proprietà <xref:System.Windows.Forms.BindingSource.Position%2A> su un valore oltre il primo o l'ultimo record, non viene generato un errore, poiché il .NET Framework non consente di impostare la posizione su un valore non compreso nei limiti dell'elenco. Se è importante per l'applicazione sapere se è stato superato il primo o l'ultimo record, includere la logica per verificare se il numero di elementi dati verrà superato.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Per verificare se è stata superata la fine o l'inizio  
  
1. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. Nel gestore è possibile verificare se il valore di posizione proposto ha superato il numero di elementi dati effettivi.  
  
     Nell'esempio seguente viene illustrato come è possibile verificare se è stato raggiunto l'ultimo elemento dati. Nell'esempio, se si è in corrispondenza dell'ultimo elemento, il pulsante **Avanti** nel form è disabilitato.  
  
    > [!NOTE]
    > Tenere presente che, se si modifica l'elenco che si sta spostando nel codice, è necessario riabilitare il pulsante **Avanti** , in modo che gli utenti possano sfogliare l'intera lunghezza del nuovo elenco. Tenere inoltre presente che l'evento <xref:System.Windows.Forms.BindingSource.PositionChanged> precedente per la <xref:System.Windows.Forms.BindingSource> specifica che si sta utilizzando deve essere associato al relativo metodo di gestione degli eventi. Di seguito è riportato un esempio di un metodo per la gestione dell'evento <xref:System.Windows.Forms.BindingSource.PositionChanged>:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Per trovare un elemento e impostarlo come elemento corrente  
  
1. Trovare il record che si desidera impostare come elemento corrente. A tale scopo, è possibile usare il metodo <xref:System.Windows.Forms.BindingSource.Find%2A> della <xref:System.Windows.Forms.BindingSource>, se l'origine dati implementa <xref:System.ComponentModel.IBindingList>. Alcuni esempi di origini dati che implementano <xref:System.ComponentModel.IBindingList> sono <xref:System.ComponentModel.BindingList%601> e <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Origini dati supportate da Windows Form](data-sources-supported-by-windows-forms.md)
- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
