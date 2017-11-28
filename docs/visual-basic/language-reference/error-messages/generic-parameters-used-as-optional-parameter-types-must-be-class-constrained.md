---
title: I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="d6982-102">I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe</span><span class="sxs-lookup"><span data-stu-id="d6982-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="d6982-103">Una routine è dichiarata con un parametro facoltativo che utilizza un parametro di tipo che non è vincolato da un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d6982-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="d6982-104">È sempre necessario fornire un valore predefinito per ogni parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d6982-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="d6982-105">Se il parametro è di un tipo riferimento, il valore facoltativo deve essere `Nothing`, ovvero un valore valido per qualsiasi tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d6982-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="d6982-106">Tuttavia, se il parametro è un tipo di valore, tale tipo deve essere un tipo di dati elementare predefinito da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d6982-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="d6982-107">Infatti, un tipo di valore composta, ad esempio una struttura definita dall'utente, non dispone di alcun valore predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="d6982-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="d6982-108">Quando si utilizza un parametro di tipo per un parametro facoltativo, è necessario garantire che sia di un tipo di riferimento per evitare la possibilità di un tipo di valore non prevede alcun valore predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="d6982-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="d6982-109">Ciò significa che è necessario vincolare il parametro di tipo con il `Class` (parola chiave) oppure con il nome di una classe specifica.</span><span class="sxs-lookup"><span data-stu-id="d6982-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="d6982-110">**ID errore:** BC32124</span><span class="sxs-lookup"><span data-stu-id="d6982-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6982-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d6982-111">To correct this error</span></span>  
  
-   <span data-ttu-id="d6982-112">Vincolare il parametro di tipo accetti solo un tipo riferimento o non utilizzare tale valore per il parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d6982-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6982-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6982-113">See Also</span></span>  
 [<span data-ttu-id="d6982-114">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6982-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="d6982-115">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="d6982-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="d6982-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="d6982-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="d6982-117">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="d6982-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="d6982-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="d6982-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="d6982-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="d6982-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
