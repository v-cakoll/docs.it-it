---
title: Cenni preliminari sul controllo DataGridView (Windows Form)
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
ms.openlocfilehash: 095c89fd305b1eeb73e2919760abe48e848c6aa0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112879"
---
# <a name="datagridview-control-overview-windows-forms"></a>Cenni preliminari sul controllo DataGridView (Windows Form)
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Con la <xref:System.Windows.Forms.DataGridView> (controllo), è possibile visualizzare e modificare dati tabulari forniti da molti tipi diversi di origini dati.  
  
 Associazione di dati per il <xref:System.Windows.Forms.DataGridView> controllo è semplice e intuitivo e in molti casi è semplice come l'impostazione di <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà. Quando si associa a un'origine dati che contiene più elenchi o tabelle, impostare il <xref:System.Windows.Forms.DataGridView.DataMember%2A> proprietà in una stringa che specifica l'elenco o una tabella per l'associazione.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, in modo che consente l'associazione alle istanze delle classi descritte nell'elenco seguente:  
  
-   Qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia, incluse le matrici unidimensionali.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IListSource> dell'interfaccia, ad esempio il <xref:System.Data.DataTable> e <xref:System.Data.DataSet> classi.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingList> dell'interfaccia, ad esempio il <xref:System.ComponentModel.BindingList%601> classe.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingListView> dell'interfaccia, ad esempio il <xref:System.Windows.Forms.BindingSource> classe.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo supporta il data binding per le proprietà degli oggetti restituiti da queste interfacce pubbliche o alla raccolta di proprietà restituito da un <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia, se implementata in oggetti restituiti.  
  
 In genere, verrà associato a un <xref:System.Windows.Forms.BindingSource> componente e associare il <xref:System.Windows.Forms.BindingSource> componente a un'altra origine dati o viene popolato con oggetti business. Il <xref:System.Windows.Forms.BindingSource> componente è l'origine dati preferito perché può eseguire l'associazione a un'ampia gamma di origini dati e di risolvere automaticamente molti problemi relativi all'associazione dati. Per altre informazioni, vedere [componente BindingSource](bindingsource-component.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo può essere usato anche nel *non associato* modalità con alcun archivio dati sottostante. Per un esempio di codice che usa un oggetto non associato <xref:System.Windows.Forms.DataGridView> controllano, vedere [procedura dettagliata: Creazione di un Windows non associato di controllo DataGridView form](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo è altamente configurabili ed estensibile e offre molte proprietà, metodi ed eventi per personalizzare l'aspetto e comportamento. Quando si desidera che l'applicazione Windows Form per visualizzare dati tabulari, è consigliabile usare la <xref:System.Windows.Forms.DataGridView> controllo prima degli altri (ad esempio, <xref:System.Windows.Forms.DataGrid>). Se si sta visualizzando una piccola griglia di valori di sola lettura o se si abilita un utente di modificare una tabella con milioni di record, il <xref:System.Windows.Forms.DataGridView> controllo fornirà all'utente una soluzione facilmente programmabile e utilizzo efficiente della memoria.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Riepilogo della tecnologia del controllo DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Vengono riepilogati <xref:System.Windows.Forms.DataGridView> controllano i concetti e l'uso di classi correlate.  
  
 [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)  
 Viene descritta l'architettura del <xref:System.Windows.Forms.DataGridView> controllo, ne viene illustrata la struttura gerarchia ed ereditarietà del tipo.  
  
 [Scenari del controllo DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Vengono descritti gli scenari più comuni in cui <xref:System.Windows.Forms.DataGridView> i controlli vengono usati.  
  
 [Directory del codice del controllo DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Vengono forniti collegamenti a esempi di codice nella documentazione per i diversi <xref:System.Windows.Forms.DataGridView> attività. Questi esempi sono suddivisi in categorie in base al tipo di attività.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)  
 Vengono descritti i tipi di colonna nei moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo utilizzato per visualizzare le informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
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
