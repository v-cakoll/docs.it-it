---
title: Notifica delle modifiche nel data binding dei Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 79ad52b6db8cb7be7f4e3162b8f726e8cbe22dcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Notifica delle modifiche nel data binding dei Windows Form
Uno dei principali concetti di data binding in Windows Form è *notifica di modifica*. Per garantire che l'origine dati e i controlli con associazione dispongano sempre dei dati più recenti, è necessario aggiungere la notifica di modifica per l'associazione dati. In particolare, si desidera garantire che i controlli con associazione vengono visualizzata una notifica delle modifiche apportate all'origine dati e l'origine dati viene informato delle modifiche apportate alle proprietà di un controllo associata.  
  
 Esistono diversi tipi di notifica delle modifiche, a seconda del tipo di associazione di dati:  
  
-   Associazione semplice in cui la proprietà di un singolo controllo viene associata a una singola istanza di un oggetto.  
  
-   Associazione basata su elenchi, che può includere una proprietà singolo controllo associata alla proprietà di un elemento in un elenco o una proprietà del controllo associato a un elenco di oggetti.  
  
 Inoltre, se si creano controlli Windows Form che si desidera utilizzare per l'associazione dati, è necessario applicare il *PropertyName*modificato modello ai controlli, in modo che le modifiche alla proprietà associata di un controllo vengono propagate al origine dati.  
  
## <a name="change-notification-for-simple-binding"></a>Notifica di modifica per l'associazione semplice  
 Per l'associazione semplice, oggetti business devono fornire la notifica di modifica quando cambia il valore di una proprietà associata. È possibile farlo esponendo un *PropertyName*evento Changed per ogni proprietà dell'oggetto business e l'oggetto business di associazione a controlli con la <xref:System.Windows.Forms.BindingSource> o il metodo preferito in cui l'oggetto business implementa il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia e genera un <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento quando cambia il valore di una proprietà. Per ulteriori informazioni, vedere [procedura: implementare l'interfaccia INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md). Quando si utilizzano oggetti che implementano il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia, non è necessario utilizzare il <xref:System.Windows.Forms.BindingSource> per associare l'oggetto a un controllo, ma tramite il <xref:System.Windows.Forms.BindingSource> è consigliato.  
  
## <a name="change-notification-for-list-based-binding"></a>Notifica di modifica per l'associazione basata su elenchi  
 Windows Form dipende da un elenco associato a modifiche delle proprietà (modifica di un valore della proprietà elemento elenco) ed elenco modificato (un elemento viene eliminato o aggiunto all'elenco) informazioni per i controlli associati. Pertanto, è necessario implementare gli elenchi usati per il data binding di <xref:System.ComponentModel.IBindingList>, che fornisce entrambi i tipi di notifica delle modifiche. Il <xref:System.ComponentModel.BindingList%601> è un'implementazione generica di <xref:System.ComponentModel.IBindingList> ed è progettata per l'utilizzo con data binding in Windows Form. È possibile creare un <xref:System.ComponentModel.BindingList%601> che contiene un tipo di oggetto business che implementa <xref:System.ComponentModel.INotifyPropertyChanged> e l'elenco convertirà automaticamente il <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventi <xref:System.ComponentModel.IBindingList.ListChanged> eventi. Se l'elenco associato non è un <xref:System.ComponentModel.IBindingList>, è necessario associare l'elenco di oggetti ai controlli Windows Form usando la <xref:System.Windows.Forms.BindingSource> componente. Il <xref:System.Windows.Forms.BindingSource> componente consentirà una conversione da elenco di proprietà simile a quello del <xref:System.ComponentModel.BindingList%601>. Per ulteriori informazioni, vedere [procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Notifica di modifica per i controlli personalizzati  
 Infine, dal lato del controllo è necessario esporre un *PropertyName*Changed per ciascuna proprietà progettata per essere associato ai dati. Le modifiche alla proprietà del controllo vengono propagate all'origine dati associata. Per altre informazioni, vedere [procedura: applicare il modello PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Origini dati supportate da Windows Form](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
