---
title: Funzioni definite dall'utente
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: f1222d9332d365c9c3c6ca2aa28cbb48e92c04e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917670"
---
# <a name="user-defined-functions"></a><span data-ttu-id="0682e-102">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="0682e-102">User-Defined Functions</span></span>
<span data-ttu-id="0682e-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono usati metodi nel modello a oggetti per rappresentare funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0682e-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="0682e-104">Per definire i metodi come funzioni, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0682e-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="0682e-105">Per altre informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="0682e-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="0682e-106">Per evitare un'eccezione <xref:System.InvalidOperationException>, è necessario che le funzioni definite dall'utente in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siano in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="0682e-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="0682e-107">Una funzione di cui è stato eseguito il wrapping come chiamata al metodo con gli attributi di mapping corretti.</span><span class="sxs-lookup"><span data-stu-id="0682e-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="0682e-108">Per altre informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0682e-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="0682e-109">Un metodo SQL statico specifico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0682e-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="0682e-110">Una funzione supportata da un metodo [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0682e-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="0682e-111">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0682e-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="0682e-112">Gli sviluppatori che usano Visual Studio Usa in genere il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping di funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0682e-112">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0682e-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0682e-113">In This Section</span></span>  
 [<span data-ttu-id="0682e-114">Procedura: Usare funzioni definite dall'utente a valori scalari</span><span class="sxs-lookup"><span data-stu-id="0682e-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="0682e-115">Viene descritto come implementare una funzione che restituisce valori scalari.</span><span class="sxs-lookup"><span data-stu-id="0682e-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="0682e-116">Procedura: Usare funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="0682e-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="0682e-117">Viene descritto come implementare una funzione che restituisce valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="0682e-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="0682e-118">Procedura: Chiamare funzioni definite dall'utente Inline</span><span class="sxs-lookup"><span data-stu-id="0682e-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="0682e-119">Viene descritto come effettuare chiamate inline alle funzioni e le differenze di esecuzione quando viene effettuata la chiamata inline.</span><span class="sxs-lookup"><span data-stu-id="0682e-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
