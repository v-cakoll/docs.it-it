---
title: Accedere a oggetti associati a righe DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 0b9a4becb78ae817141728467c1e9ea5b693476d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743171"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>Procedura: accedere a oggetti associati a righe DataGridView di Windows Form
A volte è utile visualizzare una tabella di informazioni archiviate in una raccolta di oggetti business. Quando si associa un controllo <xref:System.Windows.Forms.DataGridView> a una raccolta di questo tipo, ogni proprietà pubblica viene visualizzata nella rispettiva colonna, a meno che la proprietà non sia stata contrassegnata come non visualizzabile con <xref:System.ComponentModel.BrowsableAttribute>. Ad esempio, una raccolta di oggetti `Customer` avrebbe colonne come **Nome** e **Indirizzo**.  
  
 Se questi oggetti contengono informazioni aggiuntive e codice a cui si desidera accedere, è possibile raggiungerli tramite gli oggetti riga. Nell'esempio di codice riportato di seguito, gli utenti possono selezionare più righe e fare clic su un pulsante per inviare una fattura a ogni cliente corrispondente.  
  
### <a name="to-access-row-bound-objects"></a>Per accedere agli oggetti associati a righe  
  
- Usare la proprietà <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice completo include una semplice implementazione `Customer` e associa <xref:System.Windows.Forms.DataGridView> a un oggetto <xref:System.Collections.ArrayList> contenente alcuni oggetti `Customer`. Il gestore dell'evento <xref:System.Windows.Forms.Control.Click> di <xref:System.Windows.Forms.Button?displayProperty=nameWithType> deve accedere agli oggetti `Customer` tramite le righe, perché la raccolta di clienti non è accessibile al di fuori del gestore dell'evento <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Associare oggetti ai controlli DataGridView di Windows Forms](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
