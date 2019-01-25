---
title: Differenze tra i controlli DataGridView e DataGrid di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 02c909436bccb2af99288e522155b3f479ae782f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687718"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Differenze tra i controlli DataGridView e DataGrid di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo è un nuovo controllo che sostituisce il <xref:System.Windows.Forms.DataGrid> controllo. Il <xref:System.Windows.Forms.DataGridView> controllo fornisce numerose funzionalità di base e avanzate che non sono presenti nel <xref:System.Windows.Forms.DataGrid> controllo. Inoltre, l'architettura del <xref:System.Windows.Forms.DataGridView> controllo rende molto più semplice estendere e personalizzare rispetto di <xref:System.Windows.Forms.DataGrid> controllo.  
  
 Nella tabella seguente vengono descritte alcune delle principali funzionalità disponibili nel <xref:System.Windows.Forms.DataGridView> controllo che non sono presenti il <xref:System.Windows.Forms.DataGrid> controllo.  
  
|Funzionalità del controllo DataGridView|Descrizione|  
|----------------------------------|-----------------|  
|Più tipi di colonna|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce incorporata in più tipi di colonna rispetto di <xref:System.Windows.Forms.DataGrid> controllo. Questi tipi di colonna soddisfare le esigenze degli scenari più comuni, ma sono anche più facili da estendere o sostituire rispetto ai tipi di colonna nel <xref:System.Windows.Forms.DataGrid> controllo. Per altre informazioni, vedere [tipi di colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per visualizzare i dati|Il <xref:System.Windows.Forms.DataGrid> controllo è limitato alla visualizzazione dei dati da un'origine dati esterna. Il <xref:System.Windows.Forms.DataGridView> controllo, tuttavia, possibile visualizzare i dati non associati archiviati insieme il controllo, i dati da un'origine dati associata, o associati e non dati. È anche possibile implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo per consentire la gestione di dati personalizzati. Per altre informazioni, vedere [modalità di visualizzazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per personalizzare la visualizzazione dei dati|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce molte proprietà ed eventi che consentono di specificare la modalità di formattazione e visualizzazione dei dati. Ad esempio, è possibile modificare l'aspetto di celle, righe e colonne in base ai dati contenuti, oppure è possibile sostituire i dati di un tipo di dati con un altro tipo di dati equivalenti. Per altre informazioni, vedere [formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Più opzioni per la modifica di comportamento e l'aspetto di celle, righe, colonne e intestazione|Il <xref:System.Windows.Forms.DataGridView> controllo consente di lavorare con griglia singoli componenti in diversi modi. Ad esempio, è possibile bloccare righe e colonne per impedirne lo scorrimento; nascondere le righe, colonne e intestazioni. modificare il modo in cui vengono modificate le dimensioni di riga e colonna intestazione; modificare il modo in cui agli utenti di effettuare selezioni; e fornire le descrizioni comandi e menu di scelta rapida per le singole celle, righe e colonne.|  
  
 Il <xref:System.Windows.Forms.DataGrid> controllo viene mantenuto per compatibilità con le versioni precedenti e per particolari esigenze. Per quasi tutti gli scopi, è consigliabile usare il <xref:System.Windows.Forms.DataGridView> controllo. L'unica funzionalità che è disponibile nel <xref:System.Windows.Forms.DataGrid> controllo che non è disponibile nel <xref:System.Windows.Forms.DataGridView> controllo è la visualizzazione gerarchica delle informazioni da due tabelle correlate in un singolo controllo. È necessario utilizzare due <xref:System.Windows.Forms.DataGridView> controlli per visualizzare le informazioni provenienti da due tabelle in una relazione master/dettaglio.  
  
## <a name="upgrading-to-the-datagridview-control"></a>L'aggiornamento al controllo DataGridView  
 Se si dispone di applicazioni esistenti che usano il <xref:System.Windows.Forms.DataGrid> controllo in un semplice scenario di associazione a dati con le personalizzazioni, è possibile sostituire semplicemente il controllo precedente con il nuovo controllo. Entrambi i controlli utilizzano l'architettura di data binding Windows Forms standard, pertanto la <xref:System.Windows.Forms.DataGridView> controllo visualizzerà i dati associati senza alcuna configurazione aggiuntiva. Si potrebbe voler considerare sfruttando i vantaggi dei miglioramenti di data binding, tuttavia, mediante l'associazione dei dati a un <xref:System.Windows.Forms.BindingSource> componente, che è quindi possibile associare al <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Poiché il <xref:System.Windows.Forms.DataGridView> controllo dispone di un'architettura completamente nuova, non esiste un percorso di conversione semplice che ti consentiranno di utilizzare <xref:System.Windows.Forms.DataGrid> personalizzazioni con le <xref:System.Windows.Forms.DataGridView> controllo. Molte <xref:System.Windows.Forms.DataGrid> personalizzazioni non sono necessarie con i <xref:System.Windows.Forms.DataGridView> controllare, tuttavia, grazie alle funzionalità predefinite disponibili nel nuovo controllo. Se sono stati creati tipi di colonna personalizzata per il <xref:System.Windows.Forms.DataGrid> controllo che si desidera utilizzare con il <xref:System.Windows.Forms.DataGridView> (controllo), è necessario implementare nuovamente utilizzando la nuova architettura. Per altre informazioni, vedere [personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
- [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
