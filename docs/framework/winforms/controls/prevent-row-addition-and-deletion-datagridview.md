---
title: "Procedura: impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: 6263c92e6a981983c19e9d7f2357c581bee5ec07
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969353"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>Procedura: impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form
Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>. La proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica se la riga per i nuovi record è presente nella parte inferiore del controllo, mentre la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica se le righe possono essere rimosse. Nell'esempio di codice seguente vengono usate queste proprietà e viene impostata la proprietà <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> per rendere il controllo interamente di sola lettura.  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [procedura: impedire l'aggiunta di riga e l'eliminazione nel Windows Forms DataGridView controllo usando la finestra di progettazione](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
