---
title: Differenze tra i controlli DataGridView e DataGrid
description: Informazioni sulle diverse differenze tra le funzionalità di Windows Forms controlli DataGridView e DataGrid, nonché le differenze nell'architettura.
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 1438182d764097ae4f8fd7df046ad72c9213da19
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174588"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Differenze tra i controlli DataGridView e DataGrid di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> è un nuovo controllo che sostituisce il <xref:System.Windows.Forms.DataGrid> controllo. Il <xref:System.Windows.Forms.DataGridView> controllo offre numerose funzionalità di base e avanzate mancanti nel <xref:System.Windows.Forms.DataGrid> controllo. Inoltre, l'architettura del <xref:System.Windows.Forms.DataGridView> controllo rende molto più semplice estendere e personalizzare rispetto al <xref:System.Windows.Forms.DataGrid> controllo.  
  
 Nella tabella seguente vengono descritte alcune delle principali funzionalità disponibili nel <xref:System.Windows.Forms.DataGridView> controllo mancanti <xref:System.Windows.Forms.DataGrid> .  
  
|Funzionalità di controllo DataGridView|Descrizione|  
|----------------------------------|-----------------|  
|Più tipi di colonna|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce più tipi di colonna incorporati rispetto al <xref:System.Windows.Forms.DataGrid> controllo. Questi tipi di colonne soddisfano le esigenze degli scenari più comuni, ma sono anche più semplici da estendere o sostituire rispetto ai tipi di colonna nel <xref:System.Windows.Forms.DataGrid> controllo. Per ulteriori informazioni, vedere la pagina relativa ai [tipi di colonna nel controllo DataGridView Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per visualizzare i dati|Il <xref:System.Windows.Forms.DataGrid> controllo è limitato alla visualizzazione dei dati da un'origine dati esterna. Il <xref:System.Windows.Forms.DataGridView> controllo, tuttavia, può visualizzare i dati non associati archiviati nel controllo, i dati provenienti da un'origine dati associata o i dati associati e non associati. È anche possibile implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo per fornire la gestione dei dati personalizzata. Per altre informazioni, vedere [modalità di visualizzazione dati nel controllo DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per personalizzare la visualizzazione dei dati|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce molte proprietà ed eventi che consentono di specificare la modalità di formattazione e visualizzazione dei dati. Ad esempio, è possibile modificare l'aspetto di celle, righe e colonne a seconda dei dati in essi contenuti oppure è possibile sostituire i dati di un tipo di dati con dati equivalenti di un altro tipo. Per ulteriori informazioni, vedere [formattazione dei dati nel controllo DataGridView Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Più opzioni per la modifica dell'aspetto e del comportamento di celle, righe, colonne e intestazioni|Il <xref:System.Windows.Forms.DataGridView> controllo consente di lavorare con singoli componenti della griglia in diversi modi. È possibile, ad esempio, bloccare righe e colonne per impedirne lo scorrimento; Nascondi righe, colonne e intestazioni; modificare il modo in cui vengono regolate le dimensioni di riga, colonna e intestazione. modificare il modo in cui gli utenti effettuano le selezioni; e forniscono descrizioni comandi e menu di scelta rapida per singole celle, righe e colonne.|  
  
 Il <xref:System.Windows.Forms.DataGrid> controllo viene mantenuto per compatibilità con le versioni precedenti e per esigenze particolari. Per quasi tutti gli scopi, è necessario usare il <xref:System.Windows.Forms.DataGridView> controllo. L'unica funzionalità disponibile nel <xref:System.Windows.Forms.DataGrid> controllo che non è disponibile nel <xref:System.Windows.Forms.DataGridView> controllo è la visualizzazione gerarchica delle informazioni di due tabelle correlate in un unico controllo. <xref:System.Windows.Forms.DataGridView>Per visualizzare le informazioni di due tabelle che si trovano in una relazione master/dettaglio, è necessario utilizzare due controlli.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Aggiornamento al controllo DataGridView  
 Se si dispone di applicazioni esistenti che utilizzano il <xref:System.Windows.Forms.DataGrid> controllo in uno scenario con associazione a dati semplice senza personalizzazioni, è possibile sostituire semplicemente il vecchio controllo con il nuovo controllo. Entrambi i controlli usano l'architettura di data binding standard Windows Forms, quindi il controllo visualizzerà i <xref:System.Windows.Forms.DataGridView> dati associati senza alcuna configurazione aggiuntiva necessaria. Si consiglia di usare i miglioramenti dell'associazione dati, tuttavia, associando i dati a un <xref:System.Windows.Forms.BindingSource> componente, che è quindi possibile associare al <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [componente BindingSource](bindingsource-component.md).  
  
 Poiché il <xref:System.Windows.Forms.DataGridView> controllo ha un'architettura completamente nuova, non esiste un percorso di conversione semplice che consentirà di usare <xref:System.Windows.Forms.DataGrid> le personalizzazioni con il <xref:System.Windows.Forms.DataGridView> controllo. <xref:System.Windows.Forms.DataGrid>Tuttavia, molte personalizzazioni non sono necessarie con il controllo, a <xref:System.Windows.Forms.DataGridView> causa delle funzionalità predefinite disponibili nel nuovo controllo. Se sono stati creati tipi di colonna personalizzati per il <xref:System.Windows.Forms.DataGrid> controllo che si desidera utilizzare con il <xref:System.Windows.Forms.DataGridView> controllo, sarà necessario implementarli nuovamente utilizzando la nuova architettura. Per ulteriori informazioni, vedere [personalizzazione del controllo DataGridView Windows Forms](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView (controllo)](datagridview-control-windows-forms.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Tipi di colonna nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizzazione del controllo DataGridView Windows Form](customizing-the-windows-forms-datagridview-control.md)
