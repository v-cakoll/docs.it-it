---
title: Data binding di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: ed456807137e8cf7594bc50eb0eebb67b88e6b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800113"
---
# <a name="windows-forms-data-binding"></a>Data binding di Windows Form
Data binding in Windows Form consente di visualizzare e modificare le informazioni da un'origine dati nei controlli del form. È possibile effettuare associazioni alle origini dati tradizionali e a quasi ogni struttura che contiene dati.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Data binding e Windows Forms](data-binding-and-windows-forms.md)  
 Fornisce una panoramica del data binding in Windows Form.  
  
 [Origini dati supportate da Windows Form](data-sources-supported-by-windows-forms.md)  
 Descrive le origini dati che possono essere usate con Windows Form.  
  
 [Interfacce correlate al data binding](interfaces-related-to-data-binding.md)  
 Descrive molte delle interfacce usate con il data binding in Windows Form.  
  
 [Procedura: Esplorare dati in Windows Form](how-to-navigate-data-in-windows-forms.md)  
 Mostra come spostarsi tra gli elementi in un'origine dati.  
  
 [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)  
 Descrive i vari tipi di notifica delle modifiche per il data binding in Windows Form.  
  
 [Procedura: Implementare l'interfaccia INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)  
 Mostra come implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. L'interfaccia comunica a un controllo associato le modifiche delle proprietà di un oggetto business.  
  
 [Procedura: Applicare il modello PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)  
 Viene illustrato come applicare la *PropertyName*modello Changed alle proprietà di un controllo utente Windows Form.  
  
 [Procedura: Implementare l'interfaccia ITypedList](how-to-implement-the-itypedlist-interface.md)  
 Mostra come abilitare l'individuazione dello schema per un elenco associabile mediante l'implementazione dell'interfaccia <xref:System.ComponentModel.ITypedList>.  
  
 [Procedura: Implementare l'interfaccia IListSource](how-to-implement-the-ilistsource-interface.md)  
 Illustra come implementare l'interfaccia <xref:System.ComponentModel.IListSource> per creare una classe associabile che non implementa <xref:System.Collections.IList>, ma fornisce un elenco da un altro percorso.  
  
 [Procedura: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati](multiple-controls-bound-to-data-source-synchronized.md)  
 Mostra come gestire l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> per assicurare che tutti i controlli associati a un'origine dati rimangano sincronizzati.  
  
 [Procedura: Verificare che la riga selezionata in una tabella figlio rimanga nella posizione corretta](ensure-the-selected-row-in-a-child-table-correct.md)  
 Mostra come garantire che la riga selezionata di una tabella figlio non venga modificata quando viene apportata una modifica a un campo della tabella padre.  
  
 Vedere anche [interfacce correlate al Data Binding](interfaces-related-to-data-binding.md), [come: Esplorare dati in Windows Form](how-to-navigate-data-in-windows-forms.md), e [come: Creare un controllo con associazione semplice in un Form Windows](how-to-create-a-simple-bound-control-on-a-windows-form.md).  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Descrive la classe che rappresenta l'associazione tra un componente associabile e un'origine dati.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Descrive la classe che incapsula un'origine dati per l'associazione ai controlli.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Componente BindingSource](./controls/bindingsource-component.md)  
 Contiene un elenco di argomenti in cui viene illustrato come usare il componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Controllo DataGridView](./controls/datagridview-control-windows-forms.md)  
 Fornisce un elenco di argomenti in cui viene illustrato come usare un controllo Datagrid associabile.  
  
 Vedere anche [l'accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
