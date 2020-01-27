---
title: Usare il modello di riga per personalizzare le righe nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 35cb95f22c0caa654bf149b5fc4fd0395696a411
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728391"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Procedura: utilizzare il modello di riga personalizzare le righe nel controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> usa il modello di riga come base per tutte le righe aggiunte al controllo tramite data binding o quando si chiama il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> senza specificare una riga esistente da usare.  
  
 Il modello di riga offre un maggiore controllo sull'aspetto e sul comportamento delle righe rispetto a quanto fornito dalla proprietà <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>. Con il modello di riga, è possibile impostare qualsiasi proprietà <xref:System.Windows.Forms.DataGridViewRow>, incluso <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 In alcune situazioni è necessario utilizzare il modello di riga per ottenere un effetto specifico. Ad esempio, le informazioni sull'altezza della riga non possono essere archiviate in una <xref:System.Windows.Forms.DataGridViewCellStyle>, quindi è necessario utilizzare un modello di riga per modificare l'altezza predefinita utilizzata da tutte le righe. Il modello di riga è utile anche quando si creano classi derivate da <xref:System.Windows.Forms.DataGridViewRow> e si desidera utilizzare il tipo personalizzato quando vengono aggiunte nuove righe al controllo.  
  
> [!NOTE]
> Il modello di riga viene utilizzato solo quando vengono aggiunte righe. Non è possibile modificare le righe esistenti modificando il modello di riga.  
  
### <a name="to-use-the-row-template"></a>Per utilizzare il modello di riga  
  
- Impostare le proprietà nell'oggetto recuperato dalla proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
