---
title: Funzioni definite dall'utente
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742705"
---
# <a name="user-defined-functions"></a><span data-ttu-id="b3770-102">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="b3770-102">User-Defined Functions</span></span>
<span data-ttu-id="b3770-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono usati metodi nel modello a oggetti per rappresentare funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b3770-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="b3770-104">Per definire i metodi come funzioni, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b3770-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="b3770-105">Per altre informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="b3770-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="b3770-106">Per evitare un'eccezione <xref:System.InvalidOperationException>, è necessario che le funzioni definite dall'utente in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siano in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3770-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="b3770-107">Una funzione di cui è stato eseguito il wrapping come chiamata al metodo con gli attributi di mapping corretti.</span><span class="sxs-lookup"><span data-stu-id="b3770-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="b3770-108">Per altre informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b3770-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="b3770-109">Un metodo SQL statico specifico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3770-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="b3770-110">Una funzione supportata da un metodo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3770-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="b3770-111">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b3770-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="b3770-112">Gli sviluppatori che usano Visual Studio Usa in genere Object Relational Designer per eseguire il mapping di funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b3770-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3770-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b3770-113">In This Section</span></span>  
 [<span data-ttu-id="b3770-114">Procedura: Usare funzioni definite dall'utente a valori scalari</span><span class="sxs-lookup"><span data-stu-id="b3770-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="b3770-115">Viene descritto come implementare una funzione che restituisce valori scalari.</span><span class="sxs-lookup"><span data-stu-id="b3770-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="b3770-116">Procedura: Usare funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="b3770-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="b3770-117">Viene descritto come implementare una funzione che restituisce valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="b3770-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="b3770-118">Procedura: Chiamare funzioni definite dall'utente Inline</span><span class="sxs-lookup"><span data-stu-id="b3770-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="b3770-119">Viene descritto come effettuare chiamate inline alle funzioni e le differenze di esecuzione quando viene effettuata la chiamata inline.</span><span class="sxs-lookup"><span data-stu-id="b3770-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
