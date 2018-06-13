---
title: Differenze tra i controlli DataGridView e DataGrid di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: d0a82d5724ebe142ae080fc930665733e701e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528713"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Differenze tra i controlli DataGridView e DataGrid di Windows Form
Il <xref:System.Windows.Forms.DataGridView> è un nuovo controllo che sostituisce il <xref:System.Windows.Forms.DataGrid> controllo. Il <xref:System.Windows.Forms.DataGridView> controllo fornisce diverse funzionalità di base e avanzate che non sono presenti nel <xref:System.Windows.Forms.DataGrid> controllo. Inoltre, l'architettura del <xref:System.Windows.Forms.DataGridView> controllo rende molto più semplice estendere e personalizzare più il <xref:System.Windows.Forms.DataGrid> controllo.  
  
 Nella tabella seguente vengono descritte alcune delle funzionalità principali disponibile nel <xref:System.Windows.Forms.DataGridView> controllo che non sono presenti il <xref:System.Windows.Forms.DataGrid> controllo.  
  
|Funzionalità del controllo DataGridView|Descrizione|  
|----------------------------------|-----------------|  
|Più tipi di colonna|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce tipi di colonna più incorporate rispetto di <xref:System.Windows.Forms.DataGrid> controllo. Questi tipi di colonna soddisfare le esigenze di scenari più comuni, ma sono anche più facili estendere o sostituire rispetto ai tipi di colonna nella <xref:System.Windows.Forms.DataGrid> controllo. Per ulteriori informazioni, vedere [tipi di colonna nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per visualizzare i dati|Il <xref:System.Windows.Forms.DataGrid> il controllo è limitato alla visualizzazione dei dati da un'origine dati esterna. Il <xref:System.Windows.Forms.DataGridView> controllo, tuttavia, può visualizzare dati non associati archiviati insieme nel controllo, i dati da un'origine dati associata o i dati associati e non associati. È anche possibile implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo per fornire una gestione personalizzata dei dati. Per ulteriori informazioni, vedere [modalità di visualizzazione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per personalizzare la visualizzazione dei dati|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce molte proprietà ed eventi che consentono di specificare la modalità di formattazione e visualizzazione dati. Ad esempio, è possibile modificare l'aspetto di celle, righe e colonne in base ai dati che contengono o è possibile sostituire i dati di un tipo di dati con dati equivalente di un altro tipo. Per ulteriori informazioni, vedere [formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Più opzioni per la modifica di comportamento e l'aspetto di celle, righe, colonne e intestazione|Il <xref:System.Windows.Forms.DataGridView> controllo consente di lavorare con componenti singoli griglia in numerosi modi diversi. Ad esempio, è possibile bloccare righe e colonne per impedirne lo scorrimento; nascondere le righe, colonne e intestazioni; modificare il modo in cui vengono modificate le dimensioni di riga e colonna intestazione; modificare il modo in cui gli utenti di effettuare selezioni; e fornire le descrizioni comandi e menu di scelta rapida per singole celle, righe e colonne.|  
  
 Il <xref:System.Windows.Forms.DataGrid> controllo viene mantenuto per compatibilità con le versioni precedenti e per particolari esigenze. Per quasi tutti gli scopi, è necessario utilizzare il <xref:System.Windows.Forms.DataGridView> controllo. L'unica funzionalità disponibile nel <xref:System.Windows.Forms.DataGrid> controllo che non è disponibile nel <xref:System.Windows.Forms.DataGridView> controllo è la visualizzazione gerarchica delle informazioni da due tabelle correlate in un singolo controllo. È necessario utilizzare due <xref:System.Windows.Forms.DataGridView> controlli per visualizzare le informazioni da due tabelle in una relazione master-details.  
  
## <a name="upgrading-to-the-datagridview-control"></a>L'aggiornamento al controllo DataGridView  
 Se si dispone di applicazioni che utilizzano il <xref:System.Windows.Forms.DataGrid> controllo in un semplice scenario di associazione a dati con le personalizzazioni, è possibile sostituire semplicemente il controllo precedente con il nuovo controllo. Entrambi i controlli utilizzano l'architettura di data binding di Windows Form standard, pertanto la <xref:System.Windows.Forms.DataGridView> controllo visualizzerà i dati associati senza alcuna configurazione aggiuntiva. È possibile prendere in considerazione sfruttando la possibilità di miglioramenti di associazione dati, tuttavia, l'associazione dati per un <xref:System.Windows.Forms.BindingSource> componente, è quindi possibile associare il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [BindingSource (componente)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Poiché il <xref:System.Windows.Forms.DataGridView> controllo dispone di un'architettura completamente nuova, nessun percorso di conversione semplice che consentono di utilizzare <xref:System.Windows.Forms.DataGrid> personalizzazioni con le <xref:System.Windows.Forms.DataGridView> controllo. Molti <xref:System.Windows.Forms.DataGrid> personalizzazioni non sono necessarie con il <xref:System.Windows.Forms.DataGridView> controllare, tuttavia, grazie alle funzionalità incorporate disponibili nel controllo. Se è stato creato per i tipi di colonna personalizzati di <xref:System.Windows.Forms.DataGrid> controllo che si desidera utilizzare con il <xref:System.Windows.Forms.DataGridView> (controllo), è necessario implementarli utilizzando la nuova architettura. Per ulteriori informazioni, vedere [personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Windows.Forms.BindingSource>  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Formattazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Modalità di selezione nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
