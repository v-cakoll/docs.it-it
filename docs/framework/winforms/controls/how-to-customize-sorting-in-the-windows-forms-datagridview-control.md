---
title: Personalizzare l'ordinamento in un controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743175"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a>Procedura: personalizzare l'ordinamento nel controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> fornisce l'ordinamento automatico, tuttavia le operazioni di ordinamento possono essere personalizzate secondo le proprie esigenze. Ad esempio, è possibile usare l'ordinamento a livello di codice per creare un'interfaccia utente alternativa. È anche possibile gestire l'evento <xref:System.Windows.Forms.DataGridView.SortCompare> o chiamare l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> per una maggiore flessibilità, ad esempio per l'ordinamento di più colonne.  
  
 Gli esempi di codice seguenti illustrano questi tre approcci all'ordinamento personalizzato. Per altre informazioni, vedere [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="programmatic-sorting"></a>Ordinamento a livello di codice  
 L'esempio di codice seguente illustra un ordinamento a livello di codice che usa le proprietà <xref:System.Windows.Forms.DataGridView.SortOrder%2A> e <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> per determinare la direzione dell'ordinamento e la proprietà <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> per impostare manualmente il glifo di ordinamento. L'overload `Sort(DataGridViewColumn,ListSortDirection)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> viene usato per ordinare i dati solo in una singola colonna.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a>Ordinamento personalizzato tramite l'evento SortCompare  
 L'esempio di codice seguente illustra un ordinamento personalizzato tramite un gestore dell'evento <xref:System.Windows.Forms.DataGridView.SortCompare>. L'oggetto <xref:System.Windows.Forms.DataGridViewColumn> selezionato viene ordinato e, se esistono valori duplicati nella colonna, per determinare l'ordine finale viene usata la colonna ID.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a>Ordinamento personalizzato tramite l'interfaccia IComparer  
 L'esempio di codice seguente illustra  l'ordinamento personalizzato tramite l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>, che usa un'implementazione dell'interfaccia <xref:System.Collections.IComparer> per eseguire un ordinamento di più colonne.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi presentano i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Ordinamento di dati nel controllo DataGridView di Windows Form](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](set-the-sort-modes-for-columns-wf-datagridview-control.md)
