---
title: Modo virtuale nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: f284835578221ad1fe859f260e37bb829cd64b2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124722"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtuale nel controllo DataGridView di Windows Form
Con la modalità virtuale, è possibile gestire l'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e una cache di dati personalizzati. Per implementare la modalità virtuale, impostare il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true` e gestire uno o più eventi descritti in questo argomento. In genere, è necessario gestire almeno le `CellValueNeeded` evento, che consente il controllo per cercare i valori nella cache dei dati.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modalità di associazione e la modalità virtuale  
 Modalità virtuale è necessaria solo quando è necessario integrare o sostituire la modalità associata. In modalità di associazione, si imposta il <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà e il controllo automaticamente carica i dati dall'origine specificata e invia l'utente modifica tornarvi in qualunque momento. È possibile controllare che le colonne associate vengono visualizzati e l'origine dati gestisce in genere operazioni quali l'ordinamento.  
  
## <a name="supplementing-bound-mode"></a>Integrazione della modalità di associazione  
 È possibile integrare la modalità di associazione mediante la visualizzazione di colonne non associate con le colonne associate. Questo, talvolta chiamato "modalità mista", è utile per visualizzare ad esempio, consente di controllare i valori calcolati o interfaccia utente (UI).  
  
 Poiché le colonne non associate non sono comprese l'origine dati, vengono ignorati da operazioni di ordinamento dell'origine dati. Pertanto, quando si abilita l'ordinamento in modalità mista, è necessario gestire i dati non associati in una cache locale e implementare la modalità virtuale per consentire il <xref:System.Windows.Forms.DataGridView> controllo interagire con esso.  
  
 Per altre informazioni sull'uso della modalità virtuale per mantenere i valori nelle colonne non associate, vedere gli esempi nel <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> proprietà e <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> argomenti relativi alla classe.  
  
## <a name="replacing-bound-mode"></a>Sostituzione di modalità di associazione  
 Se la modalità associata non soddisfa le esigenze di prestazioni, è possibile gestire tutti i dati in una cache personalizzata tramite i gestori eventi in modalità virtuale. Ad esempio, è possibile utilizzare la modalità virtuale per implementare un meccanismo che consente di recuperare solo di caricamento di dati just-in-time quantità di dati da un database connesso alla rete è necessaria per ottenere prestazioni ottimali. Questo scenario è particolarmente utile quando si lavora con grandi quantità di dati tramite una connessione di rete lenta o con computer client che hanno una quantità limitata di RAM o spazio di archiviazione.  
  
 Per altre informazioni sull'uso della modalità virtuale in uno scenario just-in-time, vedere [implementazione della modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventi in modalità virtuale  
 Se i dati sono di sola lettura, la `CellValueNeeded` evento potrebbe essere l'unico evento, è necessario gestire. Gli eventi in modalità virtuale aggiuntivi consentono di abilitare funzionalità specifiche, ad esempio transazioni a livello di riga, aggiunta delle righe e l'eliminazione e modifiche dell'utente.  
  
 Alcuni standard <xref:System.Windows.Forms.DataGridView> eventi (ad esempio gli eventi che si verificano quando gli utenti di aggiungere o eliminano le righe o quando i valori delle celle sono modificati, analizzati, convalidati o formattati) sono utili in modalità virtuale, nonché. È anche possibile gestire gli eventi che consentono di mantenere i valori non viene in genere archiviati in un'origine dati associata, ad esempio testo della descrizione comando cella, cella e il testo di errore, cella e dei dati dal menu di scelta rapida riga e i dati di altezza di riga.  
  
 Per altre informazioni sull'implementazione della modalità virtuale per gestire i dati di lettura/scrittura con un ambito di commit a livello di riga, vedere [procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
 Per un esempio che implementa la modalità virtuale con un ambito a livello di cella commit, vedere il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> argomento relativo alla proprietà.  
  
 Gli eventi seguenti si verificano solo quando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è impostata su `true`.  
  
|event|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Utilizzato dal controllo per recuperare un valore di cella dalla cache dei dati per la visualizzazione. Questo evento si verifica solo per le celle delle colonne non associate.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Utilizzato dal controllo per eseguire il commit dell'input dell'utente per una cella nella cache dei dati. Questo evento si verifica solo per le celle delle colonne non associate.<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo quando si modifica un valore memorizzato nella cache all'esterno di un <xref:System.Windows.Forms.DataGridView.CellValuePushed> gestore eventi per verificare che il valore corrente viene visualizzato nel controllo e applicare le modalità di ridimensionamento automatico attualmente in vigore.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Utilizzato dal controllo per indicare la necessità di una nuova riga nella cache dei dati.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Utilizzato dal controllo per determinare se una riga contiene modifiche non sottoposte a commit.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Utilizzato dal controllo per indicare che una riga deve ripristinare i relativi valori memorizzati nella cache.|  
  
 Gli eventi seguenti sono utili in modalità virtuale, ma può essere usati indipendentemente il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> l'impostazione della proprietà.  
  
|Eventi|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Utilizzato dal controllo per indicare quando le righe vengono eliminate o aggiunte e ciò consente di conseguenza aggiornare la cache dei dati.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Utilizzato dal controllo per formattare i valori di cella per la visualizzazione e per analizzare e convalidare l'input dell'utente.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Utilizzato dal controllo per recuperare il testo della descrizione comando cella quando le <xref:System.Windows.Forms.DataGridView.DataSource%2A> viene impostata o il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è di proprietà `true`.<br /><br /> Le descrizioni comandi cella vengono visualizzate solo quando la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> valore della proprietà è `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Utilizzato dal controllo per recuperare il testo di errore di riga o cella quando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> viene impostata o il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è di proprietà `true`.<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> metodo o il <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> metodo quando si modifica il testo di errore cella o la riga per assicurarsi che il valore corrente viene visualizzato nel controllo.<br /><br /> Vengono visualizzate icone di errore delle celle e righe quando la <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> e <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> i valori delle proprietà sono `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Utilizzato dal controllo per il recupero di una cella o riga <xref:System.Windows.Forms.ContextMenuStrip> quando il controllo <xref:System.Windows.Forms.DataGridView.DataSource%2A> è impostata o il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è di proprietà `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Utilizzato dal controllo da recuperare o archiviare le informazioni sull'altezza di riga nella cache dei dati. Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> metodo quando si modificano le informazioni relative all'altezza di riga memorizzata nella cache all'esterno di un <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> gestore eventi per garantire che venga utilizzato il valore corrente nella visualizzazione del controllo.|  
  
## <a name="best-practices-in-virtual-mode"></a>Le procedure consigliate in modalità virtuale  
 Se si implementa la modalità virtuale per poter funzionare in modo efficiente con grandi quantità di dati, è inoltre opportuno verificare che si sta lavorando in modo efficiente il <xref:System.Windows.Forms.DataGridView> stesso controllo. Per altre informazioni sull'utilizzo efficiente di stili della cella, il ridimensionamento automatico, le selezioni e condivisione delle righe, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form](implementing-virtual-mode-wf-datagridview-control.md)
- [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
