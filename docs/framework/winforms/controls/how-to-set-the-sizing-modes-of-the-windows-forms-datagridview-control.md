---
title: Impostare le modalità di ridimensionamento del controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
ms.openlocfilehash: 15b084afa4149ac43d40aeae7f35f0eaff5ac0e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738396"
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a>Procedura: impostare le modalità dimensionamento del controllo DataGridView di Windows Form
Le seguenti procedure illustrano alcuni scenari comuni in cui vengono personalizzate o combinate le opzioni di ridimensionamento disponibili per il controllo <xref:System.Windows.Forms.DataGridView> e per colonne specifiche di un controllo.  
  
### <a name="to-create-a-fixed-width-column"></a>Per creare una colonna a larghezza fissa  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> su <xref:System.Windows.Forms.DataGridViewTriState.False>, la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> su `true` e la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> su un valore appropriato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a>Per creare una colonna con le dimensioni che si adattano al contenuto  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> su una modalità di ridimensionamento basata sul contenuto.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a>Per creare colonne in modalità di riempimento per valori di dimensioni e importanza diverse  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> per impostare la modalità di ridimensionamento per tutte le colonne che non eseguono l'override di questo valore. Impostare le proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> delle colonne su valori proporzionali alla larghezza media del contenuto. Impostare le proprietà <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di colonne importanti per garantire la visualizzazione parziale del contenuto.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice completo riportato di seguito illustra un'applicazione di prova che permette di comprendere meglio le opzioni di ridimensionamento descritte in questo argomento.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 Per usare questa applicazione di esempio:  
  
- Modificare le dimensioni del form. Osservare il modo in cui cambia la larghezza delle colonne in modalità di riempimento mantenendo le proporzioni indicate dai valori della proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>. Osservare il modo in cui la proprietà <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di una colonna le impedisce di cambiare quando il form è troppo piccolo.  
  
- Modificare le dimensioni delle colonne trascinando i separatori di colonna con il mouse. Osservare il modo in cui alcune colonne non possono essere ridimensionate e il modo in cui le colonne ridimensionabili non possono essere ristrette oltre la larghezza minima.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
