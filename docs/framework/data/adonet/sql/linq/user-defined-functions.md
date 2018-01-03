---
title: Funzioni definite dall'utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 833ffbbccfb35fd51ddde5dbeb4e3de3d79923ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="user-defined-functions"></a><span data-ttu-id="960c6-102">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="960c6-102">User-Defined Functions</span></span>
<span data-ttu-id="960c6-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono usati metodi nel modello a oggetti per rappresentare funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="960c6-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="960c6-104">Per definire i metodi come funzioni, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="960c6-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="960c6-105">Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="960c6-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="960c6-106">Per evitare un'eccezione <xref:System.InvalidOperationException>, è necessario che le funzioni definite dall'utente in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siano in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="960c6-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
-   <span data-ttu-id="960c6-107">Una funzione di cui è stato eseguito il wrapping come chiamata al metodo con gli attributi di mapping corretti.</span><span class="sxs-lookup"><span data-stu-id="960c6-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="960c6-108">Per ulteriori informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="960c6-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="960c6-109">Un metodo SQL statico specifico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="960c6-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
-   <span data-ttu-id="960c6-110">Una funzione supportata da un metodo [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="960c6-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="960c6-111">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="960c6-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="960c6-112">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] ricorrono in genere a [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping delle funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="960c6-112">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="960c6-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="960c6-113">In This Section</span></span>  
 [<span data-ttu-id="960c6-114">Procedura: utilizzare funzioni definite dall'utente con valori scalari</span><span class="sxs-lookup"><span data-stu-id="960c6-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="960c6-115">Viene descritto come implementare una funzione che restituisce valori scalari.</span><span class="sxs-lookup"><span data-stu-id="960c6-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="960c6-116">Procedura: utilizzare funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="960c6-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="960c6-117">Viene descritto come implementare una funzione che restituisce valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="960c6-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="960c6-118">Procedura: chiamare funzioni definite dall'utente inline</span><span class="sxs-lookup"><span data-stu-id="960c6-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="960c6-119">Viene descritto come effettuare chiamate inline alle funzioni e le differenze di esecuzione quando viene effettuata la chiamata inline.</span><span class="sxs-lookup"><span data-stu-id="960c6-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
