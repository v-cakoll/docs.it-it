---
title: Modalità di selezione nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 43f3648a9c7d64fb4fb900c7df3f01bc18d729b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539572"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modalità di selezione nel controllo DataGridView Windows Form
Talvolta si desidera l'applicazione per eseguire azioni in base alle selezioni dell'utente all'interno di un <xref:System.Windows.Forms.DataGridView> controllo. A seconda delle azioni, si desidera limitare i tipi di selezione che sono possibili. Si supponga, ad esempio, che l'applicazione è possibile stampare un report per il record attualmente selezionato. In questo caso, si desidera configurare il <xref:System.Windows.Forms.DataGridView> controllo in modo che facendo clic in un punto qualsiasi all'interno di una riga sempre selezionata l'intera riga, e che sia possibile selezionare solo una riga alla volta.  
  
 È possibile specificare le selezioni, è possibile impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà su uno dei seguenti <xref:System.Windows.Forms.DataGridViewSelectionMode> valori di enumerazione.  
  
|Valore di DataGridViewSelectionMode|Descrizione|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Fare clic su una cella viene selezionata. Intestazioni di riga e colonna non possono essere utilizzate per la selezione.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Fare clic su una cella viene selezionata. Fare clic su un'intestazione di colonna consente di selezionare l'intera colonna. Le intestazioni di colonna non possono essere utilizzate per l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Facendo clic su una cella o un'intestazione di colonna consente di selezionare l'intera colonna. Le intestazioni di colonna non possono essere utilizzate per l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Facendo clic su una cella o un'intestazione di riga seleziona l'intera riga.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modalità di selezione predefinita. Fare clic su una cella viene selezionata. Fare clic su un'intestazione di riga selezionare l'intera riga.|  
  
> [!NOTE]
>  Modifica la modalità di selezione in fase di esecuzione automatica Cancella la selezione corrente.  
  
 Per impostazione predefinita, gli utenti possono selezionare più righe, colonne o celle mediante il trascinamento con il mouse, tenendo premuto CTRL o MAIUSC durante la selezione per estendere o modificare una selezione o facendo clic sulla cella di intestazione in alto a sinistra per selezionare tutte le celle nel controllo. Per evitare questo comportamento, impostare il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> proprietà `false`.  
  
 Il <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> e <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> modalità consentire agli utenti di eliminare righe selezionandoli e premendo CANC. Gli utenti possono eliminare righe solo quando la cella corrente non è in modalità di modifica di <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> è impostata su `true`, e l'origine dati sottostante supporta l'eliminazione di righe dall'utente. Si noti che queste impostazioni non impediscono l'eliminazione di righe a livello di codice.  
  
## <a name="programmatic-selection"></a>Selezione a livello di codice  
 La modalità di selezione corrente limita il comportamento di selezione a livello di codice, nonché di selezione dell'utente. È possibile modificare la selezione corrente a livello di codice impostando la `Selected` proprietà di tutte le celle, righe o colonne presenti nella <xref:System.Windows.Forms.DataGridView> controllo. È inoltre possibile selezionare tutte le celle nel controllo tramite il <xref:System.Windows.Forms.DataGridView.SelectAll%2A> (metodo), a seconda della modalità di selezione. Per cancellare la selezione, usare il <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> metodo.  
  
 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true`, è possibile aggiungere <xref:System.Windows.Forms.DataGridView> elementi o rimuoverli dalla selezione modificando la `Selected` proprietà dell'elemento. In caso contrario, l'impostazione di `Selected` proprietà `true` per un elemento altri elementi vengono rimossi automaticamente dalla selezione.  
  
 Si noti che il valore della modifica di <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà non modifica la selezione corrente.  
  
 È possibile recuperare una raccolta delle celle attualmente selezionate, righe o colonne tramite il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> le proprietà del <xref:System.Windows.Forms.DataGridView> controllo. L'accesso a queste proprietà è inefficiente se ogni cella nel controllo è selezionata. Per evitare una riduzione delle prestazioni in questo caso, utilizzare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metodo prima. Inoltre, l'accesso a queste raccolte per determinare il numero di celle, righe o colonne possono risultare inefficiente. Utilizzare invece il <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> metodo passando la <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valore.  
  
> [!TIP]
>  Codice di esempio che illustra l'uso delle celle selezionate a livello di codice, vedere il <xref:System.Windows.Forms.DataGridView> Cenni preliminari sulla classe.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
