---
title: 'Procedura: Bloccare le colonne nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: a83c5078d67be40fda2ae3382b8124594ee78103
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966651"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a>Procedura: Bloccare le colonne nel controllo DataGridView di Windows Forms
Quando gli utenti visualizzano i dati contenuti in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form, a volte devono fare spesso riferimento a una sola colonna o a un set di colonne. Ad esempio, quando si visualizza una tabella di informazioni sui clienti che contiene molte colonne, è utile visualizzare il nome del cliente in qualsiasi momento, anche mentre le altre colonne scorrono all'esterno dell'area visibile.  
  
 A tale scopo, è possibile bloccare le colonne nel controllo. Quando si blocca una colonna, vengono bloccate anche tutte le colonne alla sua sinistra (o alla sua destra, nelle lingue scritte da destra a sinistra). Le colonne bloccate rimangono ferme mentre tutte le altre colonne possono scorrere.  
  
> [!NOTE]
> Se viene abilitato il riordinamento delle colonne, le colonne bloccate vengono considerate come un gruppo distinto dalle colonne non bloccate. Gli utenti possono riposizionare le colonne in entrambi i gruppi, ma non possono spostare una colonna da un gruppo all'altro.  
  
 La proprietà <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> di una colonna determina se la colonna è sempre visibile nella griglia.  
  
 Questa attività è supportata in Visual Studio.  Vedere [anche procedura: Bloccare le colonne nel controllo DataGridView Windows Forms usando la finestra](freeze-columns-in-the-datagrid-using-the-designer.md)di progettazione.  
  
### <a name="to-freeze-a-column-programmatically"></a>Per bloccare una colonna a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> su `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `AddToCartButton`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView Windows Forms](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
