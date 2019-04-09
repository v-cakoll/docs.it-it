---
title: . (Accesso ai membri) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 6ebedd2b381d035d199e151f64632acf7d502ff5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139711"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="e2348-103">.</span><span class="sxs-lookup"><span data-stu-id="e2348-103">.</span></span> <span data-ttu-id="e2348-104">(Accesso ai membri) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2348-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="e2348-105">L'operatore punto (.) è il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatore di accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="e2348-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="e2348-106">L'operatore di accesso ai membri viene usato per produrre il valore di una proprietà o di un campo di un'istanza del tipo di modello concettuale strutturale.</span><span class="sxs-lookup"><span data-stu-id="e2348-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2348-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2348-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2348-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e2348-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e2348-109">Istanza di un tipo di modello concettuale strutturale.</span><span class="sxs-lookup"><span data-stu-id="e2348-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="e2348-110">Proprietà o campo che appartiene a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2348-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2348-111">Note</span><span class="sxs-lookup"><span data-stu-id="e2348-111">Remarks</span></span>  
 <span data-ttu-id="e2348-112">L'operatore punto (.) può essere usato per estrarre campi da un record, analogamente all'estrazione di proprietà di un tipo di entità o complesso.</span><span class="sxs-lookup"><span data-stu-id="e2348-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="e2348-113">Se, ad esempio, un oggetto n di tipo Name è un membro del tipo Person e p è un'istanza del tipo Person, p.n è un'espressione di accesso ai membri valida che restituisce un valore di tipo Name.</span><span class="sxs-lookup"><span data-stu-id="e2348-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="e2348-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2348-114">See also</span></span>

- [<span data-ttu-id="e2348-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e2348-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
