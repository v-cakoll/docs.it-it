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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b0aa7f6f155de2c55f88b4c796ecc482d1cb84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="4770f-102">Tipi strutturati nullable (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4770f-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="4770f-103">Un'istanza `null` di un tipo strutturato è un'istanza che non esiste</span><span class="sxs-lookup"><span data-stu-id="4770f-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="4770f-104">ed è diversa da un'istanza esistente nella quale tutte le proprietà hanno valori `null`.</span><span class="sxs-lookup"><span data-stu-id="4770f-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="4770f-105">In questo argomento vengono descritti i tipi strutturati che ammettono valori Null e viene indicato quali tipi ammettono valori Null e quali modelli di codice producono istanze `null` dei tipi strutturati che ammettono valori Null.</span><span class="sxs-lookup"><span data-stu-id="4770f-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="4770f-106">Tipi strutturati che ammettono valori Null</span><span class="sxs-lookup"><span data-stu-id="4770f-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="4770f-107">Esistono tre tipi di strutture che ammettono valori Null:</span><span class="sxs-lookup"><span data-stu-id="4770f-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="4770f-108">Tipi di riga.</span><span class="sxs-lookup"><span data-stu-id="4770f-108">Row types.</span></span>  
  
-   <span data-ttu-id="4770f-109">Tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="4770f-109">Complex types.</span></span>  
  
-   <span data-ttu-id="4770f-110">Tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="4770f-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="4770f-111">Modelli di codice che producono istanze null di tipi strutturati</span><span class="sxs-lookup"><span data-stu-id="4770f-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="4770f-112">Negli scenari seguenti vengono prodotte istanze `null`:</span><span class="sxs-lookup"><span data-stu-id="4770f-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="4770f-113">Modellazione di `null` come tipo strutturato:</span><span class="sxs-lookup"><span data-stu-id="4770f-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="4770f-114">Upcast di un tipo di base a un tipo derivato:</span><span class="sxs-lookup"><span data-stu-id="4770f-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="4770f-115">Outer join in una condizione false:</span><span class="sxs-lookup"><span data-stu-id="4770f-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4770f-116">--oppure</span><span class="sxs-lookup"><span data-stu-id="4770f-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4770f-117">--oppure</span><span class="sxs-lookup"><span data-stu-id="4770f-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="4770f-118">Dereferenziamento di riferimento `null`:</span><span class="sxs-lookup"><span data-stu-id="4770f-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="4770f-119">Recupero di ANYELEMENT da una raccolta vuota:</span><span class="sxs-lookup"><span data-stu-id="4770f-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="4770f-120">Verifica delle istanze `null` dei tipi strutturati:</span><span class="sxs-lookup"><span data-stu-id="4770f-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4770f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4770f-121">See Also</span></span>  
 [<span data-ttu-id="4770f-122">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4770f-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
