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
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="9acb3-102">Procedura: impostare le modalità dimensionamento del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9acb3-102">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9acb3-103">Le seguenti procedure illustrano alcuni scenari comuni in cui vengono personalizzate o combinate le opzioni di ridimensionamento disponibili per il controllo <xref:System.Windows.Forms.DataGridView> e per colonne specifiche di un controllo.</span><span class="sxs-lookup"><span data-stu-id="9acb3-103">The following procedures demonstrate some common scenarios that customize or combine the sizing options available for the <xref:System.Windows.Forms.DataGridView> control and for specific columns in a control.</span></span>  
  
### <a name="to-create-a-fixed-width-column"></a><span data-ttu-id="9acb3-104">Per creare una colonna a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="9acb3-104">To create a fixed-width column</span></span>  
  
- <span data-ttu-id="9acb3-105">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> su <xref:System.Windows.Forms.DataGridViewTriState.False>, la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> su `true` e la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9acb3-105">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, the <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> property to <xref:System.Windows.Forms.DataGridViewTriState.False>, the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`, and the <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> property to an appropriate value.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a><span data-ttu-id="9acb3-106">Per creare una colonna con le dimensioni che si adattano al contenuto</span><span class="sxs-lookup"><span data-stu-id="9acb3-106">To create a column that adjusts its size to fit its content</span></span>  
  
- <span data-ttu-id="9acb3-107">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> su una modalità di ridimensionamento basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="9acb3-107">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to a content-based sizing mode.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a><span data-ttu-id="9acb3-108">Per creare colonne in modalità di riempimento per valori di dimensioni e importanza diverse</span><span class="sxs-lookup"><span data-stu-id="9acb3-108">To create fill-mode columns for values of varying size and importance</span></span>  
  
- <span data-ttu-id="9acb3-109">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> per impostare la modalità di ridimensionamento per tutte le colonne che non eseguono l'override di questo valore.</span><span class="sxs-lookup"><span data-stu-id="9acb3-109">Set the <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> to set the sizing mode for all columns that do not override this value.</span></span> <span data-ttu-id="9acb3-110">Impostare le proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> delle colonne su valori proporzionali alla larghezza media del contenuto.</span><span class="sxs-lookup"><span data-stu-id="9acb3-110">Set the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> properties of the columns to values that are proportional to their average content widths.</span></span> <span data-ttu-id="9acb3-111">Impostare le proprietà <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di colonne importanti per garantire la visualizzazione parziale del contenuto.</span><span class="sxs-lookup"><span data-stu-id="9acb3-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> properties of important columns to ensure partial content display.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="9acb3-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9acb3-112">Example</span></span>  
 <span data-ttu-id="9acb3-113">L'esempio di codice completo riportato di seguito illustra un'applicazione di prova che permette di comprendere meglio le opzioni di ridimensionamento descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9acb3-113">The following complete code example provides a demonstration application that can help you understand the sizing options described in this topic.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 <span data-ttu-id="9acb3-114">Per usare questa applicazione di esempio:</span><span class="sxs-lookup"><span data-stu-id="9acb3-114">To use this demonstration application:</span></span>  
  
- <span data-ttu-id="9acb3-115">Modificare le dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="9acb3-115">Change the size of the form.</span></span> <span data-ttu-id="9acb3-116">Osservare il modo in cui cambia la larghezza delle colonne in modalità di riempimento mantenendo le proporzioni indicate dai valori della proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acb3-116">Observe how the fill-mode columns change their widths while retaining the proportions indicated by the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> property values.</span></span> <span data-ttu-id="9acb3-117">Osservare il modo in cui la proprietà <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di una colonna le impedisce di cambiare quando il form è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="9acb3-117">Observe how a column's <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> prevents it from changing when the form is too small.</span></span>  
  
- <span data-ttu-id="9acb3-118">Modificare le dimensioni delle colonne trascinando i separatori di colonna con il mouse.</span><span class="sxs-lookup"><span data-stu-id="9acb3-118">Change the column sizes by dragging the column dividers with the mouse.</span></span> <span data-ttu-id="9acb3-119">Osservare il modo in cui alcune colonne non possono essere ridimensionate e il modo in cui le colonne ridimensionabili non possono essere ristrette oltre la larghezza minima.</span><span class="sxs-lookup"><span data-stu-id="9acb3-119">Observe how some columns cannot be resized, and how resizable columns cannot be made narrower than their minimum widths.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9acb3-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9acb3-120">Compiling the Code</span></span>  
 <span data-ttu-id="9acb3-121">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9acb3-121">This example requires:</span></span>  
  
- <span data-ttu-id="9acb3-122">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9acb3-122">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acb3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9acb3-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
