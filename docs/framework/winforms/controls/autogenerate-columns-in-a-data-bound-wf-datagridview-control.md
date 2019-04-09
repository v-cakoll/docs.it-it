---
title: 'Procedura: Generare automaticamente colonne in un controllo DataGridView di Windows Forms associato ai dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 4490a24047f5cce1328d68c529783a1d7692ff32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165997"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="be6ab-102">Procedura: Generare automaticamente colonne in un controllo DataGridView di Windows Forms associato ai dati</span><span class="sxs-lookup"><span data-stu-id="be6ab-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="be6ab-103">Esempio di codice seguente viene illustrato come visualizzare le colonne da un'origine dati associata in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="be6ab-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be6ab-104">Quando la <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> valore della proprietà è `true` (impostazione predefinita), un <xref:System.Windows.Forms.DataGridViewColumn> viene creato per ogni colonna nella tabella di origine dati.</span><span class="sxs-lookup"><span data-stu-id="be6ab-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="be6ab-105">Se il <xref:System.Windows.Forms.DataGridView> controllo contiene già colonne quando si impostano le <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà, verrà restituito il limite esistente colonne sono rispetto alle colonne nell'origine dati e mantenute ogni volta che viene trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="be6ab-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="be6ab-106">Le colonne non associate vengono sempre mantenute.</span><span class="sxs-lookup"><span data-stu-id="be6ab-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="be6ab-107">Le colonne associate per cui non è disponibile alcuna corrispondenza nell'origine dati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="be6ab-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="be6ab-108">Le colonne nell'origine dati per cui non è disponibile alcun elemento corrispondente al controllo generano nuovi <xref:System.Windows.Forms.DataGridViewColumn> oggetti, che vengono aggiunti alla fine del <xref:System.Windows.Forms.DataGridView.Columns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="be6ab-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be6ab-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="be6ab-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be6ab-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="be6ab-110">Compiling the Code</span></span>  
 <span data-ttu-id="be6ab-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="be6ab-111">This example requires:</span></span>  
  
-   <span data-ttu-id="be6ab-112">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `customersDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="be6ab-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="be6ab-113">Oggetto <xref:System.Data.DataSet> oggetto denominato `customersDataSet` che dispone di una tabella denominata `Customers`.</span><span class="sxs-lookup"><span data-stu-id="be6ab-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="be6ab-114">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> e <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be6ab-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6ab-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be6ab-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="be6ab-116">Visualizzazione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="be6ab-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="be6ab-117">Procedura: Rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be6ab-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
