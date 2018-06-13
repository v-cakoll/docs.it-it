---
title: Modo virtuale nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 2e5724da4442bbfcb0928c864f78744b946acc18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541021"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtuale nel controllo DataGridView di Windows Form
La modalità virtuale, è possibile gestire l'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e una cache di dati personalizzati. Per implementare la modalità virtuale, impostare il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true` e gestire uno o più eventi descritti in questo argomento. In genere si gestisce almeno il `CellValueNeeded` evento, che consente il controllo di cercare i valori nella cache dei dati.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modalità di associazione e la modalità virtuale  
 Modalità virtuale è necessaria solo quando è necessario integrare o sostituire la modalità associata. In modalità di associazione, si imposta la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà e il controllo automaticamente carica i dati dall'origine specificata e invia l'utente modifica lo. È possibile controllare che le colonne associate vengono visualizzati e l'origine dati gestisce in genere le operazioni come l'ordinamento.  
  
## <a name="supplementing-bound-mode"></a>Integrazione della modalità associata  
 È possibile integrare la modalità associata tramite la visualizzazione delle colonne non associate con le colonne associate. Questo è talvolta denominato "modalità mista" ed è utile per visualizzare, ad esempio valori calcolati o dell'interfaccia utente (UI) di controlli.  
  
 Poiché le colonne non associate sono di fuori dell'origine dati, vengono ignorate da operazioni di ordinamento dell'origine dati. Pertanto, quando si attiva l'ordinamento in modalità mista, è necessario gestire i dati non associati in una cache locale e implementare la modalità virtuale per consentire il <xref:System.Windows.Forms.DataGridView> controllo interagire con esso.  
  
 Per ulteriori informazioni sull'utilizzo della modalità virtuale per mantenere i valori nelle colonne non associate, vedere gli esempi di <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> proprietà e <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> argomenti relativi alla classe.  
  
## <a name="replacing-bound-mode"></a>Sostituzione della modalità associata  
 Se la modalità associata non soddisfa le esigenze di prestazioni, è possibile gestire tutti i dati in una cache personalizzata tramite i gestori eventi in modalità virtuale. Ad esempio, è possibile utilizzare la modalità virtuale per implementare un meccanismo che consente di recuperare solo di caricamento dei dati-in-time tutti i dati da un database in rete è necessaria per ottenere prestazioni ottimali. Questo scenario è particolarmente utile quando si lavora con grandi quantità di dati tramite una connessione di rete lenta o con computer client che dispongono di una quantità limitata di RAM o spazio di archiviazione.  
  
 Per ulteriori informazioni sull'utilizzo della modalità virtuale in uno scenario di just-in-time, vedere [implementazione della modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventi in modalità virtuale  
 Se i dati sono di sola lettura, il `CellValueNeeded` evento può essere l'unico evento sarà necessario gestire. Altri eventi in modalità virtuale consentono di abilitare funzionalità specifiche, quali transazioni a livello di riga, aggiunta delle righe e l'eliminazione e modifiche dell'utente.  
  
 Alcuni standard <xref:System.Windows.Forms.DataGridView> gli eventi (ad esempio eventi che si verificano quando gli utenti di aggiungono o eliminano le righe o quando i valori delle celle vengono modificati, analizzare, convalidare o formattati) sono utili in modalità virtuale, nonché. È anche possibile gestire gli eventi che consentono di mantenere i valori non è in genere archiviati in un'origine dati associata, ad esempio testo della descrizione comandi della cella, celle e il testo di errore e dati dei menu di scelta rapida di riga e dati altezza delle righe.  
  
 Per ulteriori informazioni sull'implementazione della modalità virtuale per gestire i dati di lettura/scrittura con un ambito di commit a livello di riga, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Per un esempio che implementa la modalità virtuale con un ambito di commit a livello di cella, vedere il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> argomento relativo alla proprietà.  
  
 Gli eventi seguenti si verificano solo quando il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è impostata su `true`.  
  
|event|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Utilizzato dal controllo per recuperare un valore di cella nella cache dei dati per la visualizzazione. Questo evento si verifica solo per le celle nelle colonne non associate.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Utilizzato dal controllo per salvare l'input dell'utente per una cella per la cache dei dati. Questo evento si verifica solo per le celle nelle colonne non associate.<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo quando si modifica un valore memorizzato nella cache di fuori di un <xref:System.Windows.Forms.DataGridView.CellValuePushed> gestore eventi per verificare che il valore corrente viene visualizzato nel controllo e applicare le modalità di ridimensionamento automatico attualmente attive.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Utilizzato dal controllo per indicare la necessità di una nuova riga nella cache dei dati.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Utilizzato dal controllo per determinare se una riga contiene modifiche non applicate.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Utilizzato dal controllo per indicare che i relativi valori memorizzati nella cache devono essere ripristinati in una riga.|  
  
 Gli eventi seguenti sono utili in modalità virtuale, ma può essere utilizzati indipendentemente dal valore di <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> l'impostazione della proprietà.  
  
|Eventi|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Utilizzato dal controllo per indicare quando le righe vengono eliminate o aggiunte, la qual cosa conseguenza aggiornare la cache dei dati.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Usato dal controllo per formattare i valori di cella per la visualizzazione e per analizzare e convalidare l'input dell'utente.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Utilizzato dal controllo per recuperare il testo della descrizione comando celle quando il <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true`.<br /><br /> Le descrizioni comandi cella vengono visualizzate solo quando il <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> valore della proprietà è `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Utilizzato dal controllo per recuperare il testo di errore di cella o riga quando il <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true`.<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> metodo o <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> metodo quando si modifica il testo di errore di riga o cella per assicurarsi che il valore corrente viene visualizzato nel controllo.<br /><br /> Vengono visualizzate icone di errore di riga e cella quando il <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> e <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> sono i valori delle proprietà `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Utilizzato dal controllo di recuperare una riga o una cella <xref:System.Windows.Forms.ContextMenuStrip> quando il controllo <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Utilizzato dal controllo per recuperare o archiviare le informazioni relative all'altezza di riga nella cache dei dati. Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> metodo quando si modificano i dati di altezza riga memorizzata nella cache di fuori di un <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> gestore eventi per assicurarsi che il valore corrente viene utilizzato nella visualizzazione del controllo.|  
  
## <a name="best-practices-in-virtual-mode"></a>Procedure consigliate in modalità virtuale  
 Se si implementa la modalità virtuale per lavorare in modo efficiente con grandi quantità di dati, è anche possibile assicurare che si utilizzano in modo efficiente il <xref:System.Windows.Forms.DataGridView> controllo stesso. Per ulteriori informazioni sull'utilizzo efficiente di stili di cella, il ridimensionamento automatico, le selezioni e condivisione delle righe, vedere [procedure consigliate per ridimensionare il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
