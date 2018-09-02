---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3881ecfd895bd22a476bdac7dd0b7c1b112092e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425185"
---
# <a name="datatablereaders"></a><span data-ttu-id="d110d-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="d110d-102">DataTableReaders</span></span>
<span data-ttu-id="d110d-103">Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d110d-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="d110d-104">Quando si crea una **DataTableReader** da un **DataTable**, risultante **DataTableReader** oggetto contiene un set di risultati con gli stessi dati il  **DataTable** da cui è stata creata, ad eccezione delle righe che sono state contrassegnate come eliminati.</span><span class="sxs-lookup"><span data-stu-id="d110d-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="d110d-105">Le colonne sono visualizzate nello stesso ordine come originale **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="d110d-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="d110d-106">Oggetto **DataTableReader** può contenere più set di risultati se è stato creato chiamando <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="d110d-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="d110d-107">I risultati sono nello stesso ordine in cui il **DataTables** nel **set di dati** dell'oggetto <xref:System.Data.DataSet.Tables%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="d110d-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d110d-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d110d-108">In This Section</span></span>  
 [<span data-ttu-id="d110d-109">Creazione di un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="d110d-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="d110d-110">Viene illustrato come creare un **DataTableReader** oggetto.</span><span class="sxs-lookup"><span data-stu-id="d110d-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="d110d-111">Esplorazione di oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="d110d-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="d110d-112">Viene descritto come utilizzare il **lettura** metodo per scorrere il contenuto di un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="d110d-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d110d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d110d-113">See Also</span></span>  
 [<span data-ttu-id="d110d-114">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d110d-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="d110d-115">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d110d-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
