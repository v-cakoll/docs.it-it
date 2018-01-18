---
title: Risoluzione dell'overload di funzioni (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cafbdd1a06ce506516fa985e9af147f55b4ea3d4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="890e0-102">Risoluzione dell'overload di funzioni (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="890e0-102">Function Overload Resolution (Entity SQL)</span></span>
<span data-ttu-id="890e0-103">In questo argomento viene descritto come vengono risolte le funzioni [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="890e0-103">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="890e0-104">È possibile definire più funzioni con lo stesso nome purché le rispettive firme siano univoche.</span><span class="sxs-lookup"><span data-stu-id="890e0-104">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="890e0-105">In una situazione di questo tipo, è necessario applicare i criteri seguenti per determinare la funzione a cui una determinata espressione fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="890e0-105">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="890e0-106">Questi criteri vengono applicati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="890e0-106">These criteria are applied in sequence.</span></span> <span data-ttu-id="890e0-107">Il primo criterio che si applica solo a un'unica funzione rappresenta la funzione risolta.</span><span class="sxs-lookup"><span data-stu-id="890e0-107">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1.  <span data-ttu-id="890e0-108">**Il parametro numero**.</span><span class="sxs-lookup"><span data-stu-id="890e0-108">**Parameter number**.</span></span> <span data-ttu-id="890e0-109">La funzione ha lo stesso numero di parametri specificato nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="890e0-109">The function has the same number of parameters specified in the expression.</span></span>  
  
2.  <span data-ttu-id="890e0-110">**Corrispondenza esatta del tipo**.</span><span class="sxs-lookup"><span data-stu-id="890e0-110">**Exact match on type**.</span></span> <span data-ttu-id="890e0-111">Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è costituito dal valore letterale Null.</span><span class="sxs-lookup"><span data-stu-id="890e0-111">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3.  <span data-ttu-id="890e0-112">**Corrispondenza del sottotipo**.</span><span class="sxs-lookup"><span data-stu-id="890e0-112">**Match on subtype**.</span></span> <span data-ttu-id="890e0-113">Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è un sottotipo del tipo di parametro oppure l'argomento è costituito dal valore letterale Null.</span><span class="sxs-lookup"><span data-stu-id="890e0-113">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="890e0-114">Nel caso in cui diverse funzioni differiscano solo nel numero di conversioni dei sottotipi richieste, la funzione con il minor numero di conversioni dei sottotipi è la funzione risolta.</span><span class="sxs-lookup"><span data-stu-id="890e0-114">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4.  <span data-ttu-id="890e0-115">**Corrispondenza del sottotipo o promozione del tipo**.</span><span class="sxs-lookup"><span data-stu-id="890e0-115">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="890e0-116">Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è un sottotipo del tipo di parametro o può essere promosso al tipo di parametro oppure l'argomento è costituito dal valore letterale Null.</span><span class="sxs-lookup"><span data-stu-id="890e0-116">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="890e0-117">Anche in questo caso, se diverse funzioni differiscono solo nel numero di promozioni e di conversioni dei sottotipi, la funzione con il minor numero di promozioni e di conversioni dei sottotipi è la funzione risolta.</span><span class="sxs-lookup"><span data-stu-id="890e0-117">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="890e0-118">Se nessuno di questi criteri consente la selezione di una singola funzione, l'espressione di chiamata della funzione è ambigua.</span><span class="sxs-lookup"><span data-stu-id="890e0-118">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="890e0-119">Anche nel caso in cui usando queste regole sia possibile estrarre una singola funzione, gli argomenti potrebbero comunque non corrispondere ai parametri.</span><span class="sxs-lookup"><span data-stu-id="890e0-119">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="890e0-120">In tal caso, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="890e0-120">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="890e0-121">Per le funzioni definite dall'utente, la definizione per una funzione inline della query ha la precedenza anche in presenza di una funzione definita dal modello con una firma che è una corrispondenza migliore per la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="890e0-121">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890e0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="890e0-122">See Also</span></span>  
 [<span data-ttu-id="890e0-123">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="890e0-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="890e0-124">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="890e0-124">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="890e0-125">Funzioni</span><span class="sxs-lookup"><span data-stu-id="890e0-125">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
