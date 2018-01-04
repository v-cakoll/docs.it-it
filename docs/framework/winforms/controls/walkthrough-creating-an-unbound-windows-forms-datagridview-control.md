---
title: 'Procedura dettagliata: creazione di un controllo DataGridView Windows Form non associato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d737959ee0ecab4c611cebf996741516fc7be031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Procedura dettagliata: creazione di un controllo DataGridView Windows Form non associato
È spesso può essere utile visualizzare dati in formato tabulare che non provengono da un database. Potrebbe ad esempio, si desidera visualizzare il contenuto di una matrice bidimensionale di stringhe. La <xref:System.Windows.Forms.DataGridView> classe fornisce un modo semplice e personalizzabile per visualizzare i dati senza associazione a un'origine dati. Questa procedura dettagliata viene illustrato come popolare un <xref:System.Windows.Forms.DataGridView> controllare e gestire l'aggiunta e l'eliminazione di righe in modalità "associata". Per impostazione predefinita, l'utente può aggiungere nuove righe. Per impedire l'aggiunta delle righe, impostare il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà `false`.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: creare un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Per utilizzare un controllo DataGridView non associato  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene le seguenti dichiarazioni di variabili e `Main` metodo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implementare un `SetupLayout` metodo nella definizione di classe del form per impostare il layout del form.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Creare un `SetupDataGridView` metodo per impostare il <xref:System.Windows.Forms.DataGridView> colonne e le proprietà.  
  
     Questo metodo aggiunge il <xref:System.Windows.Forms.DataGridView> controllo sul form <xref:System.Windows.Forms.Control.Controls%2A> insieme. Successivamente, il numero di colonne da visualizzare viene impostato mediante il <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> proprietà. Lo stile predefinito per le intestazioni di colonna è impostato tramite l'impostazione di <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, e <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> le proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> restituito dal <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> proprietà.  
  
     Vengono impostate le proprietà di layout e l'aspetto, e quindi vengono assegnati i nomi di colonna. Quando questo metodo termina, il <xref:System.Windows.Forms.DataGridView> controllo è pronto per essere compilato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Creare un `PopulateDataGridView` metodo a cui aggiungere righe di <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Ogni riga rappresenta un brano e le informazioni associate.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Con i metodi di utilità sul posto, è possibile collegare i gestori di eventi.  
  
     È necessario gestire il **Aggiungi** e **eliminare** dei pulsanti <xref:System.Windows.Forms.Control.Click> eventi, il modulo <xref:System.Windows.Forms.Form.Load> evento e <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
     Quando il **Aggiungi** del pulsante <xref:System.Windows.Forms.Control.Click> una nuova riga vuota, viene generato l'evento, viene aggiunto per il <xref:System.Windows.Forms.DataGridView>.  
  
     Quando il **eliminare** del pulsante <xref:System.Windows.Forms.Control.Click> viene generato l'evento, viene eliminata la riga selezionata, a meno che non è la riga per nuovi record, che consente all'utente di aggiungere nuove righe. Questa riga è sempre l'ultima riga di <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Quando il modulo <xref:System.Windows.Forms.Form.Load> viene generato l'evento, il `SetupLayout`, `SetupDataGridView`, e `PopulateDataGridView` vengono chiamati i metodi di utilità.  
  
     Quando il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento viene generato, ogni cella di `Date` colonna in formato data estesa, a meno che il valore della cella non può essere analizzato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per verificare il modulo  
  
-   Premere F5 per eseguire l'applicazione.  
  
     Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo che visualizza le canzoni elencate in `PopulateDataGridView`. È possibile aggiungere nuove righe con la **Aggiungi riga** e sarà possibile eliminare righe selezionate con il **Elimina riga** pulsante. La cornice <xref:System.Windows.Forms.DataGridView> controllo è l'archivio dati e i dati sono indipendenti da qualsiasi origine esterna, ad esempio un <xref:System.Data.DataSet> o una matrice.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
-   Modificare gli stili del bordo e intestazione. Per ulteriori informazioni, vedere [procedura: modificare il bordo e gli stili delle linee della griglia nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [procedura: impedire l'aggiunta delle righe e eliminazione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), e [come: rendere sola lettura di colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Controllare l'input dell'utente per errori correlati al database. Per ulteriori informazioni, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Gestire grandi set di dati utilizzando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizzare l'aspetto delle celle. Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto di celle nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Creare un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
