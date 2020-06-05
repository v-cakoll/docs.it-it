---
title: I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 273ea592e73be5d76a4ffef077e691014a108347
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402927"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="96e6e-102">I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe</span><span class="sxs-lookup"><span data-stu-id="96e6e-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="96e6e-103">Una routine viene dichiarata con un parametro facoltativo che utilizza un parametro di tipo che non è vincolato come tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="96e6e-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="96e6e-104">È sempre necessario specificare un valore predefinito per ogni parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96e6e-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="96e6e-105">Se il parametro è di un tipo di riferimento, il valore facoltativo deve essere `Nothing` , che è un valore valido per qualsiasi tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="96e6e-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="96e6e-106">Tuttavia, se il parametro è di un tipo di valore, tale tipo deve essere un tipo di dati Elementary predefinito da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96e6e-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="96e6e-107">Questo perché un tipo di valore composito, ad esempio una struttura definita dall'utente, non ha un valore predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="96e6e-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="96e6e-108">Quando si usa un parametro di tipo per un parametro facoltativo, è necessario garantire che sia di un tipo di riferimento per evitare la possibilità di un tipo di valore senza valore predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="96e6e-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="96e6e-109">Ciò significa che è necessario vincolare il parametro di tipo con la `Class` parola chiave o con il nome di una classe specifica.</span><span class="sxs-lookup"><span data-stu-id="96e6e-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="96e6e-110">**ID errore:** BC32124</span><span class="sxs-lookup"><span data-stu-id="96e6e-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96e6e-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="96e6e-111">To correct this error</span></span>  
  
- <span data-ttu-id="96e6e-112">Vincolare il parametro di tipo in modo che accetti solo un tipo riferimento o non lo usi per il parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96e6e-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e6e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96e6e-113">See also</span></span>

- [<span data-ttu-id="96e6e-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96e6e-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="96e6e-115">Type List</span><span class="sxs-lookup"><span data-stu-id="96e6e-115">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="96e6e-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="96e6e-116">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="96e6e-117">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="96e6e-117">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="96e6e-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="96e6e-118">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="96e6e-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="96e6e-119">Nothing</span></span>](../nothing.md)
