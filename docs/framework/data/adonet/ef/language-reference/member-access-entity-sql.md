---
title: . (Accesso ai membri) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c90c908e567ac05f344292411978ff0c80919a65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="772cd-103">.</span><span class="sxs-lookup"><span data-stu-id="772cd-103">.</span></span> <span data-ttu-id="772cd-104">(Accesso ai membri) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="772cd-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="772cd-105">L'operatore punto (.) è il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatore di accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="772cd-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="772cd-106">L'operatore di accesso ai membri viene usato per produrre il valore di una proprietà o di un campo di un'istanza del tipo di modello concettuale strutturale.</span><span class="sxs-lookup"><span data-stu-id="772cd-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772cd-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="772cd-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="772cd-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="772cd-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="772cd-109">Istanza di un tipo di modello concettuale strutturale.</span><span class="sxs-lookup"><span data-stu-id="772cd-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="772cd-110">Proprietà o campo che appartiene a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="772cd-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="772cd-111">Note</span><span class="sxs-lookup"><span data-stu-id="772cd-111">Remarks</span></span>  
 <span data-ttu-id="772cd-112">L'operatore punto (.) può essere usato per estrarre campi da un record, analogamente all'estrazione di proprietà di un tipo di entità o complesso.</span><span class="sxs-lookup"><span data-stu-id="772cd-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="772cd-113">Se, ad esempio, un oggetto n di tipo Name è un membro del tipo Person e p è un'istanza del tipo Person, p.n è un'espressione di accesso ai membri valida che restituisce un valore di tipo Name.</span><span class="sxs-lookup"><span data-stu-id="772cd-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="772cd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="772cd-114">See Also</span></span>  
 [<span data-ttu-id="772cd-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="772cd-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
