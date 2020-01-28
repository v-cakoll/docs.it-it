---
title: Ridimensiona automaticamente le celle quando le modifiche al contenuto nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 86e3bce993aa06546e301c6d7a7e03a31013c337
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732063"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a>Procedura: ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form
È possibile configurare il controllo <xref:System.Windows.Forms.DataGridView> per ridimensionarne automaticamente le righe, le colonne e le intestazioni quando il contenuto cambia, in modo che le dimensioni delle celle consentano sempre di visualizzare i valori senza troncarli.  
  
 Esistono molte opzioni per limitare il numero di celle usate per determinare le nuove dimensioni. Ad esempio, è possibile configurare il controllo per ridimensionare automaticamente la larghezza delle colonne solo in base ai valori nelle righe attualmente visualizzate. In questo modo è possibile lavorare sempre in modo efficiente, anche con un numero elevato di righe, sebbene in questo caso potrebbe essere necessario usare metodi di ridimensionamento come <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> per regolare le dimensioni quando si preferisce.  
  
 Per altre informazioni sul ridimensionamento automatico, vedere [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 Il seguente esempio di codice mostra le opzioni disponibili per il ridimensionamento automatico.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
