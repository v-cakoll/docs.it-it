---
title: Associare oggetti ai controlli DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: d5aa5cb64c7fb2b82d69d6c87134ee901b84f5c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746708"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a>Procedura: associare oggetti ai controlli DataGridView di Windows Form
L'esempio di codice seguente illustra come associare un insieme di oggetti a un controllo <xref:System.Windows.Forms.DataGridView> in modo che ogni oggetto venga visualizzato come riga separata. L'esempio descrive anche come visualizzare una proprietà con un tipo di enumerazione in una classe <xref:System.Windows.Forms.DataGridViewComboBoxColumn> in maniera che l'elenco a discesa della casella combinata contenga i valori di enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Accedere a oggetti associati a righe di DataGridView di Windows Form](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
