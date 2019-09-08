---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785353"
---
# <a name="datatablereaders"></a><span data-ttu-id="c4f18-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="c4f18-102">DataTableReaders</span></span>
<span data-ttu-id="c4f18-103">Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c4f18-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="c4f18-104">Quando si crea un **DataTableReader** da una **DataTable**, l'oggetto **DataTableReader** risultante contiene un set di risultati con gli stessi dati del **DataTable** da cui è stato creato, ad eccezione delle righe contrassegnate come eliminato.</span><span class="sxs-lookup"><span data-stu-id="c4f18-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="c4f18-105">Le colonne vengono visualizzate nello stesso ordine in cui si trova nella **DataTable**originale.</span><span class="sxs-lookup"><span data-stu-id="c4f18-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="c4f18-106">Un **DataTableReader** può contenere più set di <xref:System.Data.DataSet.CreateDataReader%2A>risultati se è stato creato chiamando.</span><span class="sxs-lookup"><span data-stu-id="c4f18-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="c4f18-107">I risultati sono nello stesso ordine delle **DataTable** nella <xref:System.Data.DataSet.Tables%2A> raccolta dell'oggetto **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="c4f18-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4f18-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c4f18-108">In This Section</span></span>  
 [<span data-ttu-id="c4f18-109">Creazione di un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="c4f18-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="c4f18-110">Viene illustrato come creare un oggetto **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="c4f18-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="c4f18-111">Esplorazione di oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="c4f18-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="c4f18-112">Viene descritto l'utilizzo del metodo **Read** per spostarsi nel contenuto di un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="c4f18-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f18-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4f18-113">See also</span></span>

- [<span data-ttu-id="c4f18-114">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c4f18-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="c4f18-115">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c4f18-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
