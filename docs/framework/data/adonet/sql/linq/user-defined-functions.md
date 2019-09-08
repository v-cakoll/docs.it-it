---
title: Funzioni definite dall'utente
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 40697da4fe678668f8f7ecda86abebf40da7b973
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792300"
---
# <a name="user-defined-functions"></a><span data-ttu-id="0b3f5-102">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="0b3f5-102">User-Defined Functions</span></span>
<span data-ttu-id="0b3f5-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono usati metodi nel modello a oggetti per rappresentare funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="0b3f5-104">Per definire i metodi come funzioni, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="0b3f5-105">Per ulteriori informazioni, vedere [il modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="0b3f5-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="0b3f5-106">Per evitare un'eccezione <xref:System.InvalidOperationException>, è necessario che le funzioni definite dall'utente in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siano in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b3f5-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="0b3f5-107">Una funzione di cui è stato eseguito il wrapping come chiamata al metodo con gli attributi di mapping corretti.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="0b3f5-108">Per altre informazioni, vedere [mapping basato su attributi](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0b3f5-108">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="0b3f5-109">Un metodo SQL statico specifico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b3f5-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="0b3f5-110">Funzione supportata da un metodo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="0b3f5-111">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="0b3f5-112">Gli sviluppatori che usano Visual Studio utilizzeranno in genere il Object Relational Designer per eseguire il mapping delle funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b3f5-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0b3f5-113">In This Section</span></span>  
 [<span data-ttu-id="0b3f5-114">Procedura: Usare funzioni definite dall'utente a valori scalari</span><span class="sxs-lookup"><span data-stu-id="0b3f5-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="0b3f5-115">Viene descritto come implementare una funzione che restituisce valori scalari.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="0b3f5-116">Procedura: Usare funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="0b3f5-116">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="0b3f5-117">Viene descritto come implementare una funzione che restituisce valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="0b3f5-118">Procedura: Chiamare funzioni definite dall'utente inline</span><span class="sxs-lookup"><span data-stu-id="0b3f5-118">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="0b3f5-119">Viene descritto come effettuare chiamate inline alle funzioni e le differenze di esecuzione quando viene effettuata la chiamata inline.</span><span class="sxs-lookup"><span data-stu-id="0b3f5-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
