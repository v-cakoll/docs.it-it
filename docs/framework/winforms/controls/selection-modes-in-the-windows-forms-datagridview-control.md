---
title: Modalità di selezione nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743034"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modalità di selezione nel controllo DataGridView Windows Form

In alcuni casi si desidera che l'applicazione esegua azioni in base alle selezioni dell'utente all'interno di un controllo <xref:System.Windows.Forms.DataGridView>. A seconda delle azioni, potrebbe essere necessario limitare i tipi di selezione possibili. Si supponga, ad esempio, che l'applicazione possa stampare un report per il record attualmente selezionato. In questo caso, è possibile configurare il controllo <xref:System.Windows.Forms.DataGridView> in modo che facendo clic in un punto qualsiasi all'interno di una riga si selezioni sempre l'intera riga, in modo che sia possibile selezionare solo una riga alla volta.

È possibile specificare le selezioni consentite impostando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> su uno dei valori di enumerazione <xref:System.Windows.Forms.DataGridViewSelectionMode> seguenti.

|Valore DataGridViewSelectionMode|Descrizione|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Fare clic su una cella per selezionarla. Impossibile utilizzare le intestazioni di riga e di colonna per la selezione.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Fare clic su una cella per selezionarla. Se si fa clic su un'intestazione di colonna, viene selezionata l'intera colonna. Impossibile utilizzare le intestazioni di colonna per l'ordinamento.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Se si fa clic su una cella o un'intestazione di colonna, viene selezionata l'intera colonna. Impossibile utilizzare le intestazioni di colonna per l'ordinamento.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Se si fa clic su una cella o un'intestazione di riga, viene selezionata l'intera riga.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modalità di selezione predefinita. Fare clic su una cella per selezionarla. Se si fa clic su un'intestazione di riga, viene selezionata l'intera riga.|

> [!NOTE]
> Se si modifica la modalità di selezione in fase di esecuzione, la selezione corrente viene cancellata automaticamente.

Per impostazione predefinita, gli utenti possono selezionare più righe, colonne o celle trascinando il mouse, premendo CTRL o MAIUSC mentre si seleziona per estendere o modificare una selezione oppure facendo clic sulla cella dell'intestazione in alto a sinistra per selezionare tutte le celle nel controllo. Per evitare questo comportamento, impostare la proprietà <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> su `false`.

Le modalità <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> e <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> consentono agli utenti di eliminare righe selezionandoli e premendo il tasto CANC. Gli utenti possono eliminare righe solo quando la cella corrente non è in modalità di modifica, la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> è impostata su `true`e l'origine dati sottostante supporta l'eliminazione di righe guidate dall'utente. Si noti che queste impostazioni non impediscono l'eliminazione di righe a livello di codice.

## <a name="programmatic-selection"></a>Selezione a livello di codice

La modalità di selezione corrente limita il comportamento della selezione a livello di codice e della selezione dell'utente. È possibile modificare la selezione corrente a livello di codice impostando la proprietà `Selected` di tutte le celle, le righe o le colonne presenti nel controllo <xref:System.Windows.Forms.DataGridView>. È anche possibile selezionare tutte le celle nel controllo tramite il metodo <xref:System.Windows.Forms.DataGridView.SelectAll%2A>, a seconda della modalità di selezione. Per cancellare la selezione, usare il metodo <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>.

Se la proprietà <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true`, è possibile aggiungere elementi <xref:System.Windows.Forms.DataGridView> o rimuoverli dalla selezione modificando la proprietà `Selected` dell'elemento. In caso contrario, l'impostazione della proprietà `Selected` su `true` per un elemento comporta la rimozione automatica di altri elementi dalla selezione.

Si noti che la modifica del valore della proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> non modifica la selezione corrente.

È possibile recuperare una raccolta di celle, righe o colonne attualmente selezionate tramite le proprietà <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> del controllo <xref:System.Windows.Forms.DataGridView>. L'accesso a queste proprietà non è efficiente quando si selezionano tutte le celle del controllo. Per evitare una riduzione delle prestazioni, in questo caso, usare prima il metodo <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Inoltre, l'accesso a queste raccolte per determinare il numero di celle, righe o colonne selezionate può risultare inefficiente. È invece consigliabile usare il metodo <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>, passando il valore di <xref:System.Windows.Forms.DataGridViewElementStates.Selected>.

> [!TIP]
> Il codice di esempio che illustra l'uso programmatico delle celle selezionate è disponibile nella panoramica della classe <xref:System.Windows.Forms.DataGridView>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Form](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
