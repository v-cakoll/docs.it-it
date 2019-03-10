---
title: 'Procedura: Rendere le colonne di sola lettura nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: cad80a7b242622802b5897d9903c765a877e6fd4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718359"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>Procedura: Rendere le colonne di sola lettura nel controllo DataGridView Windows Form
Non tutti i dati sono concepiti per la modifica. Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> di una colonna determina se gli utenti possono modificare le celle di tale colonna. Per informazioni su come rendere il controllo interamente di sola lettura, vedere [come: Impedire l'aggiunta di riga o eliminazione in di Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [come: Rendere le colonne di sola lettura in Windows il controllo DataGridView form usando la finestra di progettazione](make-columns-read-only-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-make-a-column-read-only-programmatically"></a>Per impostare una colonna come di sola lettura a livello di codice  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> su `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna denominata `CompanyName`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Procedura: Impedire l'aggiunta di riga e l'eliminazione nel controllo DataGridView Windows Form](prevent-row-addition-and-deletion-datagridview.md)
