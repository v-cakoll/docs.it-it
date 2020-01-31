---
title: Ridimensionare a livello di codice le celle per adattarle al contenuto nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742455"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a>Procedura: ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form
È possibile usare i metodi del controllo <xref:System.Windows.Forms.DataGridView> per ridimensionare righe, colonne e intestazioni in modo che i relativi valori vengano visualizzati per intero senza troncamenti. È possibile usare questi metodi per ridimensionare gli elementi <xref:System.Windows.Forms.DataGridView> quando è necessario. In alternativa, è possibile configurare il controllo per ridimensionare automaticamente questi elementi ogni volta che il contenuto viene modificato. Ciò può risultare inefficiente, tuttavia, quando si lavora con grandi set di dati o quando i dati vengono modificati di frequente. Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 In genere, si regolano gli elementi <xref:System.Windows.Forms.DataGridView> a livello di programmazione per adattarli al contenuto solo quando si caricano nuovi dati da un'origine dati o quando l'utente modifica un valore. Questo risulta utile per ottimizzare le prestazioni, ma anche per consentire agli utenti di ridimensionare manualmente righe e colonne con il mouse.  
  
 Il seguente esempio di codice mostra le opzioni disponibili per il ridimensionamento a livello di codice.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
