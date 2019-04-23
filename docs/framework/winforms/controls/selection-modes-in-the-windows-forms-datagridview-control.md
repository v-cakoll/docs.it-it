---
title: Modalità di selezione nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 79e13e65938252015e43b59a962d40f20963a5df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097278"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modalità di selezione nel controllo DataGridView Windows Form
A volte si desidera che l'applicazione per eseguire azioni in base alle selezioni dell'utente all'interno di un <xref:System.Windows.Forms.DataGridView> controllo. A seconda delle azioni, è possibile limitare i tipi di selezione che sono possibili. Si supponga, ad esempio, che l'applicazione può stampare un report per il record attualmente selezionato. In questo caso, è possibile configurare il <xref:System.Windows.Forms.DataGridView> controllo in modo che selezionando un punto qualsiasi all'interno di una riga sempre selezionata l'intera riga, e possa essere scelte in modo che solo una riga alla volta.  
  
 È possibile specificare le selezioni consentite impostando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà su uno dei seguenti <xref:System.Windows.Forms.DataGridViewSelectionMode> valori di enumerazione.  
  
|DataGridViewSelectionMode value|Descrizione|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Fare clic su una cella viene selezionato. Intestazioni di riga e colonna non possono essere utilizzate per la selezione.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Fare clic su una cella viene selezionato. Fare clic su un'intestazione di colonna selezionare l'intera colonna. Le intestazioni di colonna non possono essere utilizzate per l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Fare clic su una cella o un'intestazione di colonna selezionare l'intera colonna. Le intestazioni di colonna non possono essere utilizzate per l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Fare clic su una cella o in un'intestazione di riga selezionare l'intera riga.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modalità di selezione predefinita. Fare clic su una cella viene selezionato. Fare clic su un'intestazione di riga selezionare l'intera riga.|  
  
> [!NOTE]
>  Modifica la modalità di selezione in fase di esecuzione automatica Cancella la selezione corrente.  
  
 Per impostazione predefinita, gli utenti possono selezionare più righe, colonne o celle mediante il trascinamento con il mouse tenendo premuto CTRL o MAIUSC durante la selezione di estendere o modificare una selezione o facendo clic sulla cella di intestazione superiore sinistro per selezionare tutte le celle nel controllo. Per evitare questo comportamento, impostare il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> proprietà `false`.  
  
 Il <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> e <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> modalità Consenti agli utenti di eliminare righe selezionandoli e premendo il tasto CANC. Gli utenti possono eliminare le righe solo quando la cella corrente non è in modalità di modifica, la <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> è impostata su `true`, e l'origine dati sottostante supporta l'eliminazione delle righe dall'utente. Si noti che queste impostazioni non impediscono l'eliminazione di righe a livello di codice.  
  
## <a name="programmatic-selection"></a>Selezione a livello di codice  
 La modalità di selezione corrente consente di limitare il comportamento di selezione a livello di codice, nonché di selezione dell'utente. È possibile modificare la selezione corrente a livello di codice impostando la `Selected` proprietà di qualsiasi celle, righe o colonne presenti nella <xref:System.Windows.Forms.DataGridView> controllo. È anche possibile selezionare tutte le celle nel controllo tramite la <xref:System.Windows.Forms.DataGridView.SelectAll%2A> (metodo), a seconda della modalità di selezione. Per cancellare la selezione, usare il <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> (metodo).  
  
 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true`, è possibile aggiungere <xref:System.Windows.Forms.DataGridView> elementi o rimuoverli dalla selezione modificando il `Selected` proprietà dell'elemento. In caso contrario, l'impostazione di `Selected` proprietà `true` per un elemento ad altri elementi verranno rimossi automaticamente dalla selezione.  
  
 Si noti che il valore della modifica di <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà non modifica la selezione corrente.  
  
 È possibile recuperare una raccolta di celle attualmente selezionate, le righe le colonne tramite il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> delle proprietà del <xref:System.Windows.Forms.DataGridView> controllo. L'accesso a queste proprietà è inefficiente quando viene selezionato ogni cella nel controllo. Per evitare una riduzione delle prestazioni in questo caso, usare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metodo prima. Inoltre, l'accesso a queste raccolte per determinare il numero di celle, righe o colonne possono risultare inefficiente. È invece consigliabile usare la <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> metodo, passando il <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valore.  
  
> [!TIP]
>  Codice di esempio che illustra l'uso delle celle selezionate a livello di codice sono reperibili nel <xref:System.Windows.Forms.DataGridView> Cenni preliminari sulla classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare la modalità di selezione del controllo DataGridView Windows Form](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
