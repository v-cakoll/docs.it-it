---
title: Tipi strutturati nullable (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3f294088e92951e964c3daa2a105b767bca1d288
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="9bafd-102">Tipi strutturati nullable (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9bafd-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="9bafd-103">Un'istanza `null` di un tipo strutturato è un'istanza che non esiste</span><span class="sxs-lookup"><span data-stu-id="9bafd-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="9bafd-104">ed è diversa da un'istanza esistente nella quale tutte le proprietà hanno valori `null`.</span><span class="sxs-lookup"><span data-stu-id="9bafd-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="9bafd-105">In questo argomento vengono descritti i tipi strutturati che ammettono valori Null e viene indicato quali tipi ammettono valori Null e quali modelli di codice producono istanze `null` dei tipi strutturati che ammettono valori Null.</span><span class="sxs-lookup"><span data-stu-id="9bafd-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="9bafd-106">Tipi strutturati che ammettono valori Null</span><span class="sxs-lookup"><span data-stu-id="9bafd-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="9bafd-107">Esistono tre tipi di strutture che ammettono valori Null:</span><span class="sxs-lookup"><span data-stu-id="9bafd-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="9bafd-108">Tipi di riga.</span><span class="sxs-lookup"><span data-stu-id="9bafd-108">Row types.</span></span>  
  
-   <span data-ttu-id="9bafd-109">Tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="9bafd-109">Complex types.</span></span>  
  
-   <span data-ttu-id="9bafd-110">Tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="9bafd-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="9bafd-111">Modelli di codice che producono istanze null di tipi strutturati</span><span class="sxs-lookup"><span data-stu-id="9bafd-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="9bafd-112">Negli scenari seguenti vengono prodotte istanze `null`:</span><span class="sxs-lookup"><span data-stu-id="9bafd-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="9bafd-113">Modellazione di `null` come tipo strutturato:</span><span class="sxs-lookup"><span data-stu-id="9bafd-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="9bafd-114">Upcast di un tipo di base a un tipo derivato:</span><span class="sxs-lookup"><span data-stu-id="9bafd-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="9bafd-115">Outer join in una condizione false:</span><span class="sxs-lookup"><span data-stu-id="9bafd-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9bafd-116">--oppure</span><span class="sxs-lookup"><span data-stu-id="9bafd-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9bafd-117">--oppure</span><span class="sxs-lookup"><span data-stu-id="9bafd-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="9bafd-118">Dereferenziamento di riferimento `null`:</span><span class="sxs-lookup"><span data-stu-id="9bafd-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="9bafd-119">Recupero di ANYELEMENT da una raccolta vuota:</span><span class="sxs-lookup"><span data-stu-id="9bafd-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="9bafd-120">Verifica delle istanze `null` dei tipi strutturati:</span><span class="sxs-lookup"><span data-stu-id="9bafd-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9bafd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bafd-121">See Also</span></span>  
 [<span data-ttu-id="9bafd-122">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9bafd-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
