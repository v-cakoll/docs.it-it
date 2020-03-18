---
title: Delegati C# - Panoramica del linguaggio C#
description: Informazioni sull'associazione tardiva con delegati C#
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159169"
---
# <a name="delegates"></a><span data-ttu-id="751f2-103">Delegati</span><span class="sxs-lookup"><span data-stu-id="751f2-103">Delegates</span></span>

<span data-ttu-id="751f2-104">Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari.</span><span class="sxs-lookup"><span data-stu-id="751f2-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="751f2-105">I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri.</span><span class="sxs-lookup"><span data-stu-id="751f2-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="751f2-106">I delegati sono simili al concetto di puntatori a funzione che si trova in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="751f2-106">Delegates are similar to the concept of function pointers found in some other languages.</span></span> <span data-ttu-id="751f2-107">A differenza dei puntatori a funzione, i delegati sono orientati agli oggetti e indipendenti dai tipi.</span><span class="sxs-lookup"><span data-stu-id="751f2-107">Unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="751f2-108">Nell'esempio seguente viene dichiarato e usato un tipo delegato denominato `Function`.</span><span class="sxs-lookup"><span data-stu-id="751f2-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="751f2-109">Un'istanza del tipo delegato `Function` può fare riferimento a qualsiasi metodo che accetta un argomento `double` e restituisce un valore `double`.</span><span class="sxs-lookup"><span data-stu-id="751f2-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="751f2-110">Il metodo `Apply` applica una funzione specificata agli elementi di un `double[]`, restituendo un `double[]` con i risultati.</span><span class="sxs-lookup"><span data-stu-id="751f2-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="751f2-111">Nel metodo `Main`, `Apply` viene usato per applicare a `double[]` tre funzioni differenti.</span><span class="sxs-lookup"><span data-stu-id="751f2-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="751f2-112">Un delegato può fare riferimento a un metodo statico, come `Square` o `Math.Sin` nell'esempio precedente, o a un metodo di istanza, come `m.Multiply` nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="751f2-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="751f2-113">Un delegato che fa riferimento a un metodo di istanza fa riferimento anche a un oggetto particolare. Quando il metodo di istanza viene richiamato tramite il delegato, l'oggetto diventa `this` nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="751f2-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="751f2-114">I delegati possono anche essere creati utilizzando funzioni anonime, ovvero "metodi inline" che vengono creati quando vengono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="751f2-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created when declared.</span></span> <span data-ttu-id="751f2-115">Le funzioni anonime possono vedere le variabili locali dei metodi circostanti.</span><span class="sxs-lookup"><span data-stu-id="751f2-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="751f2-116">L'esempio seguente non crea una classe:The following example doesn't create a class:</span><span class="sxs-lookup"><span data-stu-id="751f2-116">The following example doesn't create a class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="751f2-117">Un delegato non conosce né si preoccupa della classe del metodo a cui fa riferimento; tutto ciò che conta è che il metodo a cui si fa riferimento abbia gli stessi parametri e lo stesso tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="751f2-117">A delegate doesn't know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="751f2-118">[Successivo](interfaces.md)
>[precedente](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="751f2-118">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
