---
title: Ordinamento di dati nel controllo DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742940"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1e3e7-102">Ordinamento dei dati nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e3e7-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="1e3e7-103">Per impostazione predefinita, gli utenti possono ordinare i dati in un controllo <xref:System.Windows.Forms.DataGridView> facendo clic sull'intestazione di una colonna casella di testo (o premendo F3 quando una cella della casella di testo è concentrata su .NET Framework 4.7.2 e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="1e3e7-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="1e3e7-104">È possibile modificare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode> di colonne specifiche per consentire agli utenti di eseguire l'ordinamento in base ad altri tipi di colonna quando è opportuno eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="1e3e7-105">È anche possibile ordinare i dati a livello di codice in base a qualsiasi colonna o a più colonne.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1e3e7-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1e3e7-106">In this section</span></span>

[<span data-ttu-id="1e3e7-107">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e3e7-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="1e3e7-108">Descrive le opzioni per l'ordinamento dei dati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="1e3e7-109">Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e3e7-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="1e3e7-110">Viene descritto come consentire agli utenti di eseguire l'ordinamento in base a colonne non ordinabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="1e3e7-111">Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e3e7-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="1e3e7-112">Viene descritto come ordinare i dati a livello di codice e come personalizzare l'ordinamento utilizzando l'evento <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> o implementando l'interfaccia <xref:System.Collections.IComparer>.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="1e3e7-113">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1e3e7-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="1e3e7-114">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="1e3e7-115">Fornisce la documentazione di riferimento per il metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="1e3e7-116">Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="1e3e7-117">Fornisce la documentazione di riferimento per l'enumerazione <xref:System.Windows.Forms.DataGridViewColumnSortMode>.</span><span class="sxs-lookup"><span data-stu-id="1e3e7-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e3e7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e3e7-118">See also</span></span>

- [<span data-ttu-id="1e3e7-119">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="1e3e7-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="1e3e7-120">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e3e7-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
