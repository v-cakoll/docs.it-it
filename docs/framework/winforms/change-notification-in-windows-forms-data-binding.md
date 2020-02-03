---
title: Notifica delle modifiche nel data binding
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746356"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Notifica delle modifiche nel data binding in Windows Form
Uno dei concetti più importanti di Windows Forms data binding è la *notifica delle modifiche*. Per assicurarsi che l'origine dati e i controlli associati includano sempre i dati più recenti, è necessario aggiungere la notifica delle modifiche per data binding. In particolare, è necessario assicurarsi che i controlli associati ricevano le modifiche apportate all'origine dati e che l'origine dati riceva notifiche delle modifiche apportate alle proprietà associate di un controllo.  
  
 Esistono diversi tipi di notifiche di modifica, a seconda del tipo di data binding:  
  
- Associazione semplice, in cui una singola proprietà del controllo è associata a una singola istanza di un oggetto.  
  
- Associazione basata su elenco, che può includere una singola proprietà del controllo associata alla proprietà di un elemento di un elenco o a una proprietà del controllo associata a un elenco di oggetti.  
  
 Inoltre, se si creano Windows Forms controlli che si desidera utilizzare per data binding, è necessario applicare il modello *PropertyName*changed ai controlli, in modo che le modifiche apportate alla proprietà associata di un controllo vengano propagate nell'origine dati.  
  
## <a name="change-notification-for-simple-binding"></a>Notifica di modifica per binding semplice  
 Per l'associazione semplice, gli oggetti business devono fornire una notifica di modifica quando il valore di una proprietà associata viene modificato. È possibile eseguire questa operazione esponendo un evento *PropertyName*Changed per ogni proprietà dell'oggetto business e associando l'oggetto business ai controlli con la <xref:System.Windows.Forms.BindingSource> o il metodo preferito in cui l'oggetto business implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> e genera un evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> quando il valore di una proprietà viene modificato. Per altre informazioni, vedere [procedura: implementare l'interfaccia INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md). Quando si usano oggetti che implementano l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>, non è necessario usare il <xref:System.Windows.Forms.BindingSource> per associare l'oggetto a un controllo, ma è consigliabile usare il <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="change-notification-for-list-based-binding"></a>Notifica di modifica per l'associazione basata su elenco  
 Windows Forms dipende da un elenco associato per fornire la modifica delle proprietà (modifiche al valore della proprietà di un elemento elenco) e l'elenco modificato (un elemento viene eliminato o aggiunto all'elenco) ai controlli associati. Pertanto, gli elenchi utilizzati per data binding devono implementare il <xref:System.ComponentModel.IBindingList>, che fornisce entrambi i tipi di notifica delle modifiche. Il <xref:System.ComponentModel.BindingList%601> è un'implementazione generica di <xref:System.ComponentModel.IBindingList> ed è progettato per essere utilizzato con Windows Forms data binding. È possibile creare un <xref:System.ComponentModel.BindingList%601> contenente un tipo di oggetto business che implementa <xref:System.ComponentModel.INotifyPropertyChanged> e l'elenco convertirà automaticamente gli eventi di <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> in <xref:System.ComponentModel.IBindingList.ListChanged> eventi. Se l'elenco associato non è una <xref:System.ComponentModel.IBindingList>, è necessario associare l'elenco di oggetti ai controlli Windows Forms tramite il componente <xref:System.Windows.Forms.BindingSource>. Il componente <xref:System.Windows.Forms.BindingSource> fornirà una conversione da proprietà a elenco simile a quella della <xref:System.ComponentModel.BindingList%601>. Per ulteriori informazioni, vedere [procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Notifica di modifica per i controlli personalizzati  
 Infine, dal lato del controllo è necessario esporre un evento *PropertyName*Changed per ogni proprietà progettata per essere associata ai dati. Le modifiche apportate alla proprietà del controllo vengono quindi propagate nell'origine dati associata. Per altre informazioni, vedere [procedura: applicare il modello NomeProprietàChanged](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Associazione ai dati di Windows Form](windows-forms-data-binding.md)
- [Origini dati supportate da Windows Form](data-sources-supported-by-windows-forms.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
