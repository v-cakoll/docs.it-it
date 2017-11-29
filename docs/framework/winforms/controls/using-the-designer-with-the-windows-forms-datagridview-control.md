---
title: Utilizzo della finestra di progettazione con il controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b29904954a593607a7872c0b59265bbf241dce98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="1827a-102">Utilizzo della finestra di progettazione con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1827a-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1827a-103">Visual Studio fornisce il supporto per il `DataGridView` controllo che consente di eseguire numerose attività di impostazione senza scrivere codice.</span><span class="sxs-lookup"><span data-stu-id="1827a-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="1827a-104">Tali attività includono il controllo a un'origine dati, la modifica delle colonne utilizzato per visualizzare i dati di associazione e a regolare l'aspetto e il comportamento di base del controllo.</span><span class="sxs-lookup"><span data-stu-id="1827a-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1827a-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1827a-105">In This Section</span></span>  
 [<span data-ttu-id="1827a-106">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-107">Viene descritto come utilizzare il **Add Columns** e **Modifica colonne** finestre di dialogo per compilare e modificare la raccolta di colonne.</span><span class="sxs-lookup"><span data-stu-id="1827a-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="1827a-108">Procedura: Associare dati al controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-109">Viene descritto come utilizzare il **Scegli origine dati** opzione smart tag del controllo per connettersi ai dati.</span><span class="sxs-lookup"><span data-stu-id="1827a-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="1827a-110">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-111">Viene descritto come utilizzare il **Modifica colonne** la finestra di dialogo per riordinare le colonne.</span><span class="sxs-lookup"><span data-stu-id="1827a-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="1827a-112">Procedura: Modificare il tipo di una colonna DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="1827a-113">Viene descritto come utilizzare il **Modifica colonne** la finestra di dialogo per modificare i tipi di colonna.</span><span class="sxs-lookup"><span data-stu-id="1827a-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="1827a-114">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-115">Viene descritto come utilizzare smart tag del controllo per consentire agli utenti di ridisporre le colonne.</span><span class="sxs-lookup"><span data-stu-id="1827a-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="1827a-116">Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-117">Viene descritto come utilizzare il **Modifica colonne** la finestra di dialogo per impedire lo scorrimento di colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="1827a-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="1827a-118">Procedura: Nascondere le colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-119">Viene descritto come utilizzare il **Modifica colonne** la finestra di dialogo per nascondere colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="1827a-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="1827a-120">Procedura: Rendere le colonne di sola lettura nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-121">Viene descritto come utilizzare il **Modifica colonne** la finestra di dialogo per impedire agli utenti di modificare i valori in colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="1827a-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="1827a-122">Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-123">Viene descritto come utilizzare smart tag del controllo per impedire agli utenti di aggiungere o eliminare righe.</span><span class="sxs-lookup"><span data-stu-id="1827a-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="1827a-124">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1827a-125">Viene descritto come utilizzare il **Generatore CellStyle** la finestra di dialogo per creare un aspetto ledger nel controllo.</span><span class="sxs-lookup"><span data-stu-id="1827a-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="1827a-126">Procedura: Impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1827a-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="1827a-127">Viene descritto come utilizzare il **Generatore CellStyle** formatta la finestra di dialogo per impostare l'aspetto di base e la visualizzazione dei dati per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1827a-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1827a-128">Riferimento</span><span class="sxs-lookup"><span data-stu-id="1827a-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="1827a-129">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1827a-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1827a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1827a-130">See Also</span></span>  
 [<span data-ttu-id="1827a-131">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="1827a-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
