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
ms.openlocfilehash: 03ba4e13cb014ca03f80781e6630d41c01ae6251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529964"
---
# <a name="datagridview-control-overview-windows-forms"></a>Cenni preliminari sul controllo DataGridView (Windows Form)
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Con il <xref:System.Windows.Forms.DataGridView> (controllo), è possibile visualizzare e modificare i dati tabulari da molti tipi diversi di origini dati.  
  
 Associazione di dati per il <xref:System.Windows.Forms.DataGridView> controllo è semplice e intuitivo e in molti casi è semplice come l'impostazione di <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà. Quando si associa a un'origine dati contenente più elenchi o tabelle, impostare il <xref:System.Windows.Forms.DataGridView.DataMember%2A> proprietà in una stringa che specifica l'elenco o una tabella da associare.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, quindi eseguirà l'associazione a istanze delle classi descritte nell'elenco seguente:  
  
-   Qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia, incluse le matrici unidimensionali.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IListSource> interfaccia, ad esempio il <xref:System.Data.DataTable> e <xref:System.Data.DataSet> classi.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio la <xref:System.ComponentModel.BindingList%601> classe.  
  
-   Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingListView> interfaccia, ad esempio la <xref:System.Windows.Forms.BindingSource> classe.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo supporta il data binding per le proprietà pubbliche degli oggetti restituiti da queste interfacce o per la raccolta di proprietà restituito da un <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia, se implementata in oggetti restituiti.  
  
 In genere, verrà associato a un <xref:System.Windows.Forms.BindingSource> componente e associare il <xref:System.Windows.Forms.BindingSource> componente a un'altra origine dati o viene popolato con gli oggetti business. Il <xref:System.Windows.Forms.BindingSource> componente è l'origine dati preferita in quanto è possibile associare a una vasta gamma di origini dati e di risolvere molti problemi relativi all'associazione dati automaticamente. Per ulteriori informazioni, vedere [BindingSource (componente)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo può essere utilizzato anche *non associato* modalità con alcun archivio dati sottostante. Per un esempio di codice che utilizza un oggetto non associato <xref:System.Windows.Forms.DataGridView> di controllo, vedere [procedura dettagliata: creazione di un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo è particolarmente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzare l'aspetto e comportamento. Quando si desidera che l'applicazione Windows Form per visualizzare i dati tabulari, è consigliabile utilizzare il <xref:System.Windows.Forms.DataGridView> controllo prima di altre (ad esempio, <xref:System.Windows.Forms.DataGrid>). Se si intende visualizzare una griglia di piccole dimensioni dei valori di sola lettura o se si sta abilitando un utente di modificare una tabella con milioni di record, il <xref:System.Windows.Forms.DataGridView> controllo offre una soluzione facilmente programmabile e utilizzo efficiente della memoria.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Riepilogo della tecnologia del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Riepiloga <xref:System.Windows.Forms.DataGridView> controllare i concetti e l'utilizzo di classi correlate.  
  
 [Architettura del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Viene descritta l'architettura del <xref:System.Windows.Forms.DataGridView> controllo, ne viene illustrata la struttura di gerarchia e l'ereditarietà di tipo.  
  
 [Scenari del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Vengono descritti gli scenari più comuni in cui <xref:System.Windows.Forms.DataGridView> i controlli vengono utilizzati.  
  
 [Directory del codice del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Vengono forniti collegamenti a esempi di codice nella documentazione per i diversi <xref:System.Windows.Forms.DataGridView> attività. Questi esempi sono suddivisi in categorie in base al tipo di attività.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Vengono descritti i tipi di colonna in Windows Form <xref:System.Windows.Forms.DataGridView> controllo utilizzato per visualizzare informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come popolare il controllo con i dati manualmente o da un'origine dati esterna.  
  
 [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.  
  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come usare il controllo in modo efficiente per evitare problemi di prestazioni quando si lavora con grandi quantità di dati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Funzionalità predefinite nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [Gestione predefinita di tastiera e mouse nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
