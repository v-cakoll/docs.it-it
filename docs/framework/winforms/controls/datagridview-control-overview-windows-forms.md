---
title: Cenni preliminari sul controllo DataGridView
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 74de5b449525be9ff93fcbef0ddabd041470177c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742490"
---
# <a name="datagridview-control-overview-windows-forms"></a>Panoramica del controllo DataGridView (Windows Form)
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Con il controllo <xref:System.Windows.Forms.DataGridView> è possibile visualizzare e modificare i dati tabulari da molti tipi diversi di origini dati.  
  
 L'associazione di dati al controllo <xref:System.Windows.Forms.DataGridView> è semplice e intuitiva e, in molti casi, è semplice come impostare la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>. Quando si esegue l'associazione a un'origine dati che contiene più elenchi o tabelle, impostare la proprietà <xref:System.Windows.Forms.DataGridView.DataMember%2A> su una stringa che specifica l'elenco o la tabella a cui eseguire l'associazione.  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> supporta il modello standard di data binding Windows Forms, in modo che venga associato alle istanze delle classi descritte nell'elenco seguente:  
  
- Qualsiasi classe che implementa l'interfaccia <xref:System.Collections.IList>, incluse le matrici unidimensionali.  
  
- Qualsiasi classe che implementa l'interfaccia <xref:System.ComponentModel.IListSource>, ad esempio le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet>.  
  
- Qualsiasi classe che implementa l'interfaccia <xref:System.ComponentModel.IBindingList>, ad esempio la classe <xref:System.ComponentModel.BindingList%601>.  
  
- Qualsiasi classe che implementa l'interfaccia <xref:System.ComponentModel.IBindingListView>, ad esempio la classe <xref:System.Windows.Forms.BindingSource>.  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> supporta data binding alle proprietà pubbliche degli oggetti restituiti da queste interfacce o alla raccolta Properties restituita da un'interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor>, se implementata sugli oggetti restituiti.  
  
 In genere, si eseguirà l'associazione a un componente <xref:System.Windows.Forms.BindingSource> e si associa il componente <xref:System.Windows.Forms.BindingSource> a un'altra origine dati o lo si popola con gli oggetti business. Il componente <xref:System.Windows.Forms.BindingSource> è l'origine dati preferita perché può essere associato a un'ampia gamma di origini dati e può risolvere automaticamente molti problemi di data binding. Per ulteriori informazioni, vedere [componente BindingSource](bindingsource-component.md).  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> può essere usato anche in modalità non *associata* , senza archivio dati sottostante. Per un esempio di codice in cui viene usato un controllo <xref:System.Windows.Forms.DataGridView> non associato, vedere [procedura dettagliata: creazione di un controllo DataGridView Windows Forms non associato](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> è altamente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzarne l'aspetto e il comportamento. Quando si desidera che la Windows Forms Application visualizzi dati tabulari, è consigliabile utilizzare il controllo <xref:System.Windows.Forms.DataGridView> prima di altri, ad esempio <xref:System.Windows.Forms.DataGrid>. Se si visualizza una piccola griglia di valori di sola lettura o se si consente a un utente di modificare una tabella con milioni di record, il controllo <xref:System.Windows.Forms.DataGridView> fornirà una soluzione facilmente programmabile e efficiente per la memoria.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Riepilogo della tecnologia del controllo DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Riepiloga <xref:System.Windows.Forms.DataGridView> concetti di controllo e l'utilizzo di classi correlate.  
  
 [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)  
 Descrive l'architettura del controllo <xref:System.Windows.Forms.DataGridView>, che spiega la gerarchia dei tipi e la struttura di ereditarietà.  
  
 [Scenari del controllo DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Vengono descritti gli scenari più comuni in cui vengono utilizzati i controlli <xref:System.Windows.Forms.DataGridView>.  
  
 [Directory del codice del controllo DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Vengono forniti collegamenti a esempi di codice nella documentazione per diverse attività di <xref:System.Windows.Forms.DataGridView>. Questi esempi sono suddivisi in categorie in base al tipo di attività.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)  
 Vengono illustrati i tipi di colonna nel controllo Windows Forms <xref:System.Windows.Forms.DataGridView> utilizzato per visualizzare le informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come popolare il controllo con i dati manualmente o da un'origine dati esterna.  
  
 [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.  
  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come usare il controllo in modo efficiente per evitare problemi di prestazioni quando si lavora con grandi quantità di dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Funzionalità predefinite nel controllo DataGridView di Windows Form](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Gestione predefinita di tastiera e mouse nel controllo DataGridView di Windows Form](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
