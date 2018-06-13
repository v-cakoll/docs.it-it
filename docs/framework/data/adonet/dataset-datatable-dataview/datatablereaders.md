---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 8305629bb267805cd79455e2edf990e72a12dc10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756098"
---
# <a name="datatablereaders"></a><span data-ttu-id="301cc-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="301cc-102">DataTableReaders</span></span>
<span data-ttu-id="301cc-103">Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="301cc-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="301cc-104">Quando si crea un **DataTableReader** da un **DataTable**, il valore risultante **DataTableReader** oggetto contiene un set di risultati con gli stessi dati il  **DataTable** da cui è stato creato, ad eccezione delle righe che sono state contrassegnate come eliminate.</span><span class="sxs-lookup"><span data-stu-id="301cc-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="301cc-105">Le colonne vengono visualizzate nello stesso ordine utilizzato originale **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="301cc-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="301cc-106">Oggetto **DataTableReader** può contenere più set di risultati, se è stato creato chiamando <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="301cc-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="301cc-107">I risultati sono nello stesso ordine di **DataTable** nel **DataSet** dell'oggetto <xref:System.Data.DataSet.Tables%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="301cc-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="301cc-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="301cc-108">In This Section</span></span>  
 [<span data-ttu-id="301cc-109">Creazione di un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="301cc-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="301cc-110">Viene illustrato come creare un **DataTableReader** oggetto.</span><span class="sxs-lookup"><span data-stu-id="301cc-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="301cc-111">Esplorazione di oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="301cc-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="301cc-112">Viene descritto come utilizzare il **lettura** metodo per scorrere il contenuto di un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="301cc-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301cc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="301cc-113">See Also</span></span>  
 [<span data-ttu-id="301cc-114">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="301cc-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="301cc-115">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="301cc-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
