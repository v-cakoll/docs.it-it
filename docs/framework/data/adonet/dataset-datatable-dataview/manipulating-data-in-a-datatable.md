---
title: Manipolazione di dati in un oggetto DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eb4ecf8996836fde443216f1d9225e8f113b0b7f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="16dbd-102">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="16dbd-103">Dopo aver creato un tipo <xref:System.Data.DataTable> in un tipo <xref:System.Data.DataSet>, è possibile usarlo esattamente come una tabella in un database.</span><span class="sxs-lookup"><span data-stu-id="16dbd-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="16dbd-104">È possibile aggiungere, visualizzare, modificare ed eliminare i dati della tabella, monitorare errori ed eventi ed eseguire query nei dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="16dbd-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="16dbd-105">Quando si modificano i dati in un **DataTable**, è inoltre possibile verificare se le modifiche sono accurate e stabilire se a livello di programmazione accettare o rifiutare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="16dbd-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16dbd-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="16dbd-106">In This Section</span></span>  
 [<span data-ttu-id="16dbd-107">Aggiunta di dati a un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="16dbd-108">Viene spiegato come creare nuove righe e aggiungerle a una tabella.</span><span class="sxs-lookup"><span data-stu-id="16dbd-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="16dbd-109">Visualizzazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="16dbd-110">Viene descritto come accedere ai dati di una riga, incluse le versioni originali e correnti dei dati.</span><span class="sxs-lookup"><span data-stu-id="16dbd-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="16dbd-111">Metodo Load</span><span class="sxs-lookup"><span data-stu-id="16dbd-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="16dbd-112">Viene descritto come utilizzare il **carico** metodo da riempire un **DataTable** con righe.</span><span class="sxs-lookup"><span data-stu-id="16dbd-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="16dbd-113">Modifiche a DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="16dbd-114">Viene spiegato come modificare i dati di una riga, inclusa la sospensione delle modifiche a una riga fino a quando le modifiche proposte non saranno verificate e accettate.</span><span class="sxs-lookup"><span data-stu-id="16dbd-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="16dbd-115">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="16dbd-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="16dbd-116">Vengono fornite informazioni sui diversi stati di una riga.</span><span class="sxs-lookup"><span data-stu-id="16dbd-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="16dbd-117">Eliminazione di DataRow</span><span class="sxs-lookup"><span data-stu-id="16dbd-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="16dbd-118">Viene descritto come rimuovere una riga da una tabella.</span><span class="sxs-lookup"><span data-stu-id="16dbd-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="16dbd-119">Informazioni sugli errori di riga</span><span class="sxs-lookup"><span data-stu-id="16dbd-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="16dbd-120">Viene spiegato come inserire informazioni sugli errori in ciascuna riga, per consentire la risoluzione dei problemi relativi ai dati all'interno di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="16dbd-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="16dbd-121">Oggetti AcceptChange e RejectChange</span><span class="sxs-lookup"><span data-stu-id="16dbd-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="16dbd-122">Viene spiegato come accettare o rifiutare le modifiche apportate a una riga.</span><span class="sxs-lookup"><span data-stu-id="16dbd-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16dbd-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16dbd-123">See Also</span></span>  
 [<span data-ttu-id="16dbd-124">DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="16dbd-125">Gestione di eventi DataTable</span><span class="sxs-lookup"><span data-stu-id="16dbd-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="16dbd-126">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="16dbd-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
