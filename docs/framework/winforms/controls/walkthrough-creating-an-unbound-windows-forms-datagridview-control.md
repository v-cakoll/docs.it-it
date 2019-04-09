---
title: 'Procedura dettagliata: Creazione di un controllo DataGridView di Windows Forms non associato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: 375ac3bd3a178cc059239cf84209ebbf5d6aca11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220578"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Procedura dettagliata: Creazione di un controllo DataGridView di Windows Forms non associato
Spesso è possibile visualizzare i dati in formato tabulare che provengono da un database. È possibile, ad esempio visualizzare il contenuto di una matrice di stringhe bidimensionale. Il <xref:System.Windows.Forms.DataGridView> classe fornisce un modo semplice e altamente personalizzabile per visualizzare i dati senza associazione a un'origine dati. Questa procedura dettagliata illustra come popolare un <xref:System.Windows.Forms.DataGridView> controllare e gestire l'aggiunta e l'eliminazione di righe in modalità "associata". Per impostazione predefinita, l'utente può aggiungere nuove righe. Per impedire l'aggiunta delle righe, impostare il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> è di proprietà `false`.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un controllo DataGridView di Windows non associato form](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Usare un controllo DataGridView non associato  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene le seguenti dichiarazioni di variabili e `Main` (metodo).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implementare un `SetupLayout` metodo nella definizione di classe del form per impostare il layout del form.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Creare un `SetupDataGridView` metodo per impostare il <xref:System.Windows.Forms.DataGridView> colonne e le proprietà.  
  
     Questo metodo aggiunge innanzitutto il <xref:System.Windows.Forms.DataGridView> controllo del modulo <xref:System.Windows.Forms.Control.Controls%2A> raccolta. Successivamente, il numero di colonne da visualizzare viene impostato utilizzando il <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> proprietà. Lo stile predefinito per le intestazioni di colonna è impostato, impostando il <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, e <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> le proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> restituito dal <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> proprietà.  
  
     Vengono impostate le proprietà di layout e l'aspetto, e quindi vengono assegnati i nomi delle colonne. Quando questo metodo termina, il <xref:System.Windows.Forms.DataGridView> controllo è pronto per essere popolato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Creare un `PopulateDataGridView` metodo a cui aggiungere righe di <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Ogni riga rappresenta una classe song e le informazioni associate.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Con i metodi di utilità posto, è possibile collegare i gestori eventi.  
  
     Verranno gestiti i **Add** e **eliminare** degli pulsanti <xref:System.Windows.Forms.Control.Click> eventi, il modulo <xref:System.Windows.Forms.Form.Load> evento e il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
     Quando la **Add** del pulsante <xref:System.Windows.Forms.Control.Click> evento viene generato, una nuova riga vuota, viene aggiunto per il <xref:System.Windows.Forms.DataGridView>.  
  
     Quando la **eliminare** del pulsante <xref:System.Windows.Forms.Control.Click> viene generato l'evento, viene eliminata la riga selezionata, a meno che non è la riga per i nuovi record, che consente all'utente di aggiungere nuove righe. Questa riga è sempre l'ultima riga il <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Quando il form <xref:System.Windows.Forms.Form.Load> evento viene generato, il `SetupLayout`, `SetupDataGridView`, e `PopulateDataGridView` vengono chiamati i metodi di utilità.  
  
     Quando la <xref:System.Windows.Forms.DataGridView.CellFormatting> evento viene generato, ogni cella nella `Date` colonna è formattata come data estesa, a meno che non è possibile analizzare il valore della cella.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il form  
  
-   Premere F5 per eseguire l'applicazione.  
  
     Si noterà una <xref:System.Windows.Forms.DataGridView> controllo che vengono visualizzate le canzoni elencate in `PopulateDataGridView`. È possibile aggiungere nuove righe con la **Aggiungi riga** e sarà possibile eliminare le righe selezionate con i **Elimina riga** pulsante. La cornice <xref:System.Windows.Forms.DataGridView> controllo è l'archivio dati e i dati sono indipendente da qualsiasi origine esterna, ad esempio un <xref:System.Data.DataSet> o una matrice.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
-   Modificare gli stili del bordo e l'intestazione. Per altre informazioni, vedere [Procedura: Modificare il bordo e gli stili delle linee della griglia nella finestra di Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [Procedura: Impedire l'aggiunta di riga o eliminazione in di Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), e [come: Rendere le colonne di sola lettura nella finestra di Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Verificare l'input dell'utente per gli errori correlati al database. Per altre informazioni, vedere [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nella finestra di Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Gestire set di dati molto grandi usando la modalità virtuale. Per altre informazioni, vedere [Procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md) e [come: Impostare stili di cella predefiniti per i Windows Form controllo DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Visualizzazione di dati nel controllo DataGridView Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un controllo DataGridView di Windows Forms non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
