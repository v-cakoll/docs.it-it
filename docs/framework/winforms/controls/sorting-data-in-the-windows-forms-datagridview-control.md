---
title: Ordinamento dati nel controllo DataGridView Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2327c6d9696bc5fb54943eb8bbce9d4795a378b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="603d6-102">Ordinamento dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="603d6-102">Sorting Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="603d6-103">Per impostazione predefinita, gli utenti possono ordinare i dati in un `DataGridView` controllo facendo clic sull'intestazione di colonna di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="603d6-103">By default, users can sort the data in a `DataGridView` control by clicking the header of a text box column.</span></span> <span data-ttu-id="603d6-104">È possibile modificare il `SortMode` proprietà di colonne specifiche per consentire agli utenti di ordinare gli altri tipi di colonna quando è consigliabile eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="603d6-104">You can modify the `SortMode` property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="603d6-105">È inoltre possibile ordinare i dati a livello di codice da qualsiasi colonna o da più colonne.</span><span class="sxs-lookup"><span data-stu-id="603d6-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="603d6-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="603d6-106">In This Section</span></span>  
 [<span data-ttu-id="603d6-107">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="603d6-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="603d6-108">Vengono descritte le opzioni per l'ordinamento dei dati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="603d6-108">Describes the options for sorting data in the control.</span></span>  
  
 [<span data-ttu-id="603d6-109">Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="603d6-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 <span data-ttu-id="603d6-110">Viene descritto come consentire agli utenti di ordinamento di colonne che non sono ordinabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="603d6-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>  
  
 [<span data-ttu-id="603d6-111">Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="603d6-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="603d6-112">Viene descritto come ordinare i dati a livello di programmazione e come personalizzare l'ordinamento utilizzando il <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> evento o implementando il <xref:System.Collections.IComparer> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="603d6-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="603d6-113">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="603d6-113">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="603d6-114">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="603d6-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <span data-ttu-id="603d6-115">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="603d6-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="603d6-116">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="603d6-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumnSortMode>  
 <span data-ttu-id="603d6-117">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="603d6-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603d6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="603d6-118">See Also</span></span>  
 [<span data-ttu-id="603d6-119">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="603d6-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="603d6-120">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="603d6-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
