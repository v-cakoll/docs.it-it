---
title: Creazione di un controllo DataGridView non associato
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
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740183"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Procedura dettagliata: creazione di un controllo DataGridView Windows Form non associato
È possibile che si desideri visualizzare spesso dati tabulari che non provengono da un database di. È ad esempio possibile che si desideri visualizzare il contenuto di una matrice bidimensionale di stringhe. La classe <xref:System.Windows.Forms.DataGridView> fornisce un modo semplice e altamente personalizzabile per visualizzare i dati senza binding a un'origine dati. In questa procedura dettagliata viene illustrato come popolare un controllo <xref:System.Windows.Forms.DataGridView> e come gestire l'aggiunta e l'eliminazione di righe in modalità "non associata". Per impostazione predefinita, l'utente può aggiungere nuove righe. Per evitare l'aggiunta di righe, impostare la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> è `false`.  
  
 Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un controllo DataGridView Windows Forms non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Per usare un controllo DataGridView non associato  
  
1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene le seguenti dichiarazioni di variabili e `Main` metodo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Implementare un metodo di `SetupLayout` nella definizione di classe del form per impostare il layout del modulo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Creare un metodo di `SetupDataGridView` per impostare le colonne e le proprietà <xref:System.Windows.Forms.DataGridView>.  
  
     Questo metodo aggiunge prima di tutto il controllo <xref:System.Windows.Forms.DataGridView> alla raccolta di <xref:System.Windows.Forms.Control.Controls%2A> del form. Il numero di colonne da visualizzare viene quindi impostato utilizzando la proprietà <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>. Lo stile predefinito per le intestazioni di colonna viene impostato impostando le proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>e <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> del <xref:System.Windows.Forms.DataGridViewCellStyle> restituito dalla proprietà <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>.  
  
     Vengono impostate le proprietà layout e aspetto, quindi vengono assegnati i nomi delle colonne. Quando questo metodo viene chiuso, il controllo <xref:System.Windows.Forms.DataGridView> è pronto per essere popolato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Creare un `PopulateDataGridView` metodo per aggiungere righe al controllo <xref:System.Windows.Forms.DataGridView>.  
  
     Ogni riga rappresenta un brano e le relative informazioni associate.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. Con i metodi di utilità disponibili, è possibile associare i gestori eventi.  
  
     Si gestiranno i pulsanti **Aggiungi** ed **Elimina** ' <xref:System.Windows.Forms.Control.Click> eventi, l'evento <xref:System.Windows.Forms.Form.Load> del modulo e l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del controllo <xref:System.Windows.Forms.DataGridView>.  
  
     Quando viene generato l'evento <xref:System.Windows.Forms.Control.Click> del pulsante **Aggiungi** , viene aggiunta una nuova riga vuota al <xref:System.Windows.Forms.DataGridView>.  
  
     Quando viene generato l'evento <xref:System.Windows.Forms.Control.Click> del pulsante **Elimina** , la riga selezionata viene eliminata, a meno che non si tratti della riga per i nuovi record, che consente all'utente di aggiungere nuove righe. Questa riga è sempre l'ultima riga nel controllo <xref:System.Windows.Forms.DataGridView>.  
  
     Quando viene generato l'evento <xref:System.Windows.Forms.Form.Load> del modulo, vengono chiamati i metodi di utilità `SetupLayout`, `SetupDataGridView`e `PopulateDataGridView`.  
  
     Quando viene generato l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting>, ogni cella nella colonna `Date` viene formattata come data estesa, a meno che non sia possibile analizzare il valore della cella.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Test dell'applicazione  
 È ora possibile testare il form per assicurarsi che si comportano come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il modulo  
  
- Premere F5 per eseguire l'applicazione.  
  
     Verrà visualizzato un controllo <xref:System.Windows.Forms.DataGridView> che Visualizza i brani elencati nella `PopulateDataGridView`. È possibile aggiungere nuove righe con il pulsante **Aggiungi riga** ed è possibile eliminare le righe selezionate con il pulsante **Elimina riga** . Il controllo <xref:System.Windows.Forms.DataGridView> non associato è l'archivio dati e i relativi dati sono indipendenti da qualsiasi origine esterna, ad esempio un <xref:System.Data.DataSet> o una matrice.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione offre una conoscenza di base delle funzionalità del controllo <xref:System.Windows.Forms.DataGridView>. È possibile personalizzare l'aspetto e il comportamento del controllo <xref:System.Windows.Forms.DataGridView> in diversi modi:  
  
- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Abilitare o limitare l'input dell'utente per il controllo <xref:System.Windows.Forms.DataGridView>. Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: rendere le colonne di sola lettura nel controllo DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Controllare l'input dell'utente per gli errori correlati al database. Per ulteriori informazioni, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un controllo DataGridView di Windows Form non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
