---
title: 'Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: cb3a826262a49a8653e3a344bd126d434f2522dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073043"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms
Il <xref:System.Windows.Forms.DataGridView> controllo Usa il modello di riga come base per tutte le righe da aggiungere al controllo tramite associazione dati o quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> metodo senza specificare una riga esistente da usare.  
  
 Il modello di riga offre un maggiore controllo sull'aspetto e comportamento di righe di <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> fornisce proprietà. Con il modello di riga, è possibile impostare qualsiasi <xref:System.Windows.Forms.DataGridViewRow> proprietà, tra cui <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Esistono alcune situazioni in cui è necessario utilizzare il modello di riga per ottenere un risultato particolare. Ad esempio, le informazioni sull'altezza di riga non può essere archiviati un <xref:System.Windows.Forms.DataGridViewCellStyle>, pertanto è necessario usare un modello di riga per modificare l'altezza predefinita per tutte le righe. Il modello di riga è utile anche quando si creano il proprio classi derivate da <xref:System.Windows.Forms.DataGridViewRow> e si desidera utilizzare un tipo personalizzato al controllo vengono aggiunte nuove righe.  
  
> [!NOTE]
>  Il modello di riga viene utilizzato solo quando vengono aggiunte righe. È possibile modificare le righe esistenti modificando il modello di riga.  
  
### <a name="to-use-the-row-template"></a>Usare il modello di riga  
  
-   Impostare le proprietà per l'oggetto recuperato dal <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
