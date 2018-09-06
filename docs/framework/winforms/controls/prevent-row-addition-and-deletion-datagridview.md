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
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875375"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6c82e-102">Procedura: impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c82e-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6c82e-103">Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6c82e-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6c82e-104">La proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica se la riga per i nuovi record è presente nella parte inferiore del controllo, mentre la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica se le righe possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="6c82e-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="6c82e-105">Nell'esempio di codice seguente vengono usate queste proprietà e viene impostata la proprietà <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> per rendere il controllo interamente di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6c82e-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="6c82e-106">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c82e-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="6c82e-107">Vedere anche [procedura: impedire l'aggiunta di riga e l'eliminazione nel Windows Forms DataGridView controllo usando la finestra di progettazione](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6c82e-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c82e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c82e-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6c82e-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6c82e-109">Compiling the Code</span></span>  
 <span data-ttu-id="6c82e-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c82e-110">This example requires:</span></span>  
  
-   <span data-ttu-id="6c82e-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="6c82e-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="6c82e-112">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c82e-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c82e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c82e-113">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="6c82e-114">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c82e-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
