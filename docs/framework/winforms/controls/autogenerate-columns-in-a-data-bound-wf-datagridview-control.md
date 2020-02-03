---
title: Genera automaticamente colonne nel controllo DataGridView con associazione a dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746241"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="be673-102">Procedura: generare automaticamente le colonne in un controllo DataGridView associato ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="be673-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="be673-103">Nell'esempio di codice riportato di seguito viene illustrato come visualizzare colonne da un'origine dati associata in un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="be673-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be673-104">Quando il <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> valore della proprietà è `true` (impostazione predefinita), viene creata una <xref:System.Windows.Forms.DataGridViewColumn> per ogni colonna nella tabella dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="be673-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="be673-105">Se il controllo <xref:System.Windows.Forms.DataGridView> dispone già di colonne quando si imposta la proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, le colonne associate esistenti vengono confrontate con le colonne nell'origine dati e mantenute ogni volta che viene stabilita una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="be673-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="be673-106">Le colonne non associate vengono sempre mantenute.</span><span class="sxs-lookup"><span data-stu-id="be673-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="be673-107">Le colonne associate per le quali non è presente alcuna corrispondenza nell'origine dati vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="be673-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="be673-108">Le colonne nell'origine dati per cui non esiste alcuna corrispondenza nel controllo generano nuovi oggetti <xref:System.Windows.Forms.DataGridViewColumn>, che vengono aggiunti alla fine della raccolta di <xref:System.Windows.Forms.DataGridView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="be673-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be673-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="be673-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be673-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="be673-110">Compiling the Code</span></span>  
 <span data-ttu-id="be673-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="be673-111">This example requires:</span></span>  
  
- <span data-ttu-id="be673-112">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `customersDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="be673-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="be673-113">Oggetto <xref:System.Data.DataSet> denominato `customersDataSet` con una tabella denominata `Customers`.</span><span class="sxs-lookup"><span data-stu-id="be673-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="be673-114">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> e <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be673-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be673-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be673-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="be673-116">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="be673-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="be673-117">Procedura: Rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="be673-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
