---
title: Differenze tra i controlli DataGridView e DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745963"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Differenze tra i controlli DataGridView e DataGrid Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> è un nuovo controllo che sostituisce il controllo <xref:System.Windows.Forms.DataGrid>. Il controllo <xref:System.Windows.Forms.DataGridView> offre numerose funzionalità di base e avanzate mancanti nel controllo <xref:System.Windows.Forms.DataGrid>. Inoltre, l'architettura del controllo <xref:System.Windows.Forms.DataGridView> rende molto più semplice estendere e personalizzare rispetto al controllo <xref:System.Windows.Forms.DataGrid>.  
  
 Nella tabella seguente vengono descritte alcune delle principali funzionalità disponibili nel controllo <xref:System.Windows.Forms.DataGridView> mancanti nel controllo <xref:System.Windows.Forms.DataGrid>.  
  
|Funzionalità di controllo DataGridView|Descrizione|  
|----------------------------------|-----------------|  
|Più tipi di colonna|Il controllo <xref:System.Windows.Forms.DataGridView> fornisce più tipi di colonna incorporati rispetto al controllo <xref:System.Windows.Forms.DataGrid>. Questi tipi di colonne soddisfano le esigenze degli scenari più comuni, ma sono anche più semplici da estendere o sostituire rispetto ai tipi di colonna nel controllo <xref:System.Windows.Forms.DataGrid>. Per ulteriori informazioni, vedere la pagina relativa ai [tipi di colonna nel controllo DataGridView Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per visualizzare i dati|Il controllo <xref:System.Windows.Forms.DataGrid> è limitato alla visualizzazione dei dati da un'origine dati esterna. Il controllo <xref:System.Windows.Forms.DataGridView>, tuttavia, può visualizzare i dati non associati archiviati nel controllo, i dati da un'origine dati associata o i dati associati e non associati. È anche possibile implementare la modalità virtuale nel controllo <xref:System.Windows.Forms.DataGridView> per fornire la gestione dati personalizzata. Per altre informazioni, vedere [modalità di visualizzazione dati nel controllo DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Diversi modi per personalizzare la visualizzazione dei dati|Il controllo <xref:System.Windows.Forms.DataGridView> fornisce molte proprietà ed eventi che consentono di specificare la modalità di formattazione e visualizzazione dei dati. Ad esempio, è possibile modificare l'aspetto di celle, righe e colonne a seconda dei dati in essi contenuti oppure è possibile sostituire i dati di un tipo di dati con dati equivalenti di un altro tipo. Per ulteriori informazioni, vedere [formattazione dei dati nel controllo DataGridView Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Più opzioni per la modifica dell'aspetto e del comportamento di celle, righe, colonne e intestazioni|Il controllo <xref:System.Windows.Forms.DataGridView> consente di lavorare con singoli componenti della griglia in diversi modi. È possibile, ad esempio, bloccare righe e colonne per impedirne lo scorrimento; Nascondi righe, colonne e intestazioni; modificare il modo in cui vengono regolate le dimensioni di riga, colonna e intestazione. modificare il modo in cui gli utenti effettuano le selezioni; e forniscono descrizioni comandi e menu di scelta rapida per singole celle, righe e colonne.|  
  
 Il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per esigenze particolari. Per quasi tutti gli scopi, è necessario usare il controllo <xref:System.Windows.Forms.DataGridView>. L'unica funzionalità disponibile nel controllo <xref:System.Windows.Forms.DataGrid> che non è disponibile nel controllo <xref:System.Windows.Forms.DataGridView> è la visualizzazione gerarchica delle informazioni di due tabelle correlate in un unico controllo. È necessario utilizzare due controlli <xref:System.Windows.Forms.DataGridView> per visualizzare le informazioni di due tabelle che si trovano in una relazione master/dettagli.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Aggiornamento al controllo DataGridView  
 Se si dispone di applicazioni esistenti che utilizzano il controllo <xref:System.Windows.Forms.DataGrid> in un semplice scenario associato a dati senza personalizzazioni, è possibile sostituire semplicemente il vecchio controllo con il nuovo controllo. Entrambi i controlli usano l'architettura di data binding standard Windows Forms, quindi il controllo <xref:System.Windows.Forms.DataGridView> visualizzerà i dati associati senza alcuna configurazione aggiuntiva necessaria. Si consiglia di sfruttare i miglioramenti dell'associazione dati, tuttavia, associando i dati a un componente <xref:System.Windows.Forms.BindingSource>, che è quindi possibile associare al controllo <xref:System.Windows.Forms.DataGridView>. Per ulteriori informazioni, vedere [componente BindingSource](bindingsource-component.md).  
  
 Poiché il controllo <xref:System.Windows.Forms.DataGridView> ha un'architettura completamente nuova, non esiste un percorso di conversione semplice che consentirà di usare <xref:System.Windows.Forms.DataGrid> personalizzazioni con il controllo <xref:System.Windows.Forms.DataGridView>. Molte <xref:System.Windows.Forms.DataGrid> personalizzazioni non sono necessarie con il controllo <xref:System.Windows.Forms.DataGridView>, tuttavia, a causa delle funzionalità predefinite disponibili nel nuovo controllo. Se sono stati creati tipi di colonna personalizzati per il controllo <xref:System.Windows.Forms.DataGrid> che si desidera utilizzare con il controllo <xref:System.Windows.Forms.DataGridView>, sarà necessario implementarli nuovamente utilizzando la nuova architettura. Per ulteriori informazioni, vedere [personalizzazione del controllo DataGridView Windows Forms](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)
