---
title: Associazione ai dati di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60a9f66fec64ceda71dd5b70211b897c84113429
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-data-binding"></a>Associazione ai dati di Windows Form
Data binding in Windows Form consente di visualizzare e modificare le informazioni da un'origine dati nei controlli del form. È possibile effettuare associazioni alle origini dati tradizionali e a quasi ogni struttura che contiene dati.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 Fornisce una panoramica del data binding in Windows Form.  
  
 [Origini dati supportate da Windows Form](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 Descrive le origini dati che possono essere usate con Windows Form.  
  
 [Interfacce correlate al data binding](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 Descrive molte delle interfacce usate con il data binding in Windows Form.  
  
 [Procedura: Esplorare dati in Windows Form](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 Mostra come spostarsi tra gli elementi in un'origine dati.  
  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Descrive i vari tipi di notifica delle modifiche per il data binding in Windows Form.  
  
 [Procedura: Implementare l'interfaccia INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 Mostra come implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. L'interfaccia comunica a un controllo associato le modifiche delle proprietà di un oggetto business.  
  
 [Procedura: Applicare il modello PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 Viene illustrato come applicare il *PropertyName*modello Changed alle proprietà di un controllo utente Windows Form.  
  
 [Procedura: Implementare l'interfaccia ITypedList](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 Mostra come abilitare l'individuazione dello schema per un elenco associabile mediante l'implementazione dell'interfaccia <xref:System.ComponentModel.ITypedList>.  
  
 [Procedura: Implementare l'interfaccia IListSource](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 Illustra come implementare l'interfaccia <xref:System.ComponentModel.IListSource> per creare una classe associabile che non implementa <xref:System.Collections.IList>, ma fornisce un elenco da un altro percorso.  
  
 [Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 Mostra come gestire l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> per assicurare che tutti i controlli associati a un'origine dati rimangano sincronizzati.  
  
 [Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 Mostra come garantire che la riga selezionata di una tabella figlio non venga modificata quando viene apportata una modifica a un campo della tabella padre.  
  
 Vedere anche [interfacce correlate all'associazione di dati](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [procedura: passare dati in Windows Form](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [procedura: creare un controllo con associazione semplice in un Windows Form](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Descrive la classe che rappresenta l'associazione tra un componente associabile e un'origine dati.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Descrive la classe che incapsula un'origine dati per l'associazione ai controlli.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Componente BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 Contiene un elenco di argomenti in cui viene illustrato come usare il componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Controllo DataGridView](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 Fornisce un elenco di argomenti in cui viene illustrato come usare un controllo Datagrid associabile.  
  
 Vedere anche [accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
