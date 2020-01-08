---
title: Delegati C# - Panoramica del linguaggio C#
description: Informazioni sull'associazione tardiva con delegati C#
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 317d3ee6fb1350824fa9b3b4d0e3e851780ce4d4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346875"
---
# <a name="delegates"></a><span data-ttu-id="17901-103">Delegati</span><span class="sxs-lookup"><span data-stu-id="17901-103">Delegates</span></span>

<span data-ttu-id="17901-104">Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari.</span><span class="sxs-lookup"><span data-stu-id="17901-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="17901-105">I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri.</span><span class="sxs-lookup"><span data-stu-id="17901-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="17901-106">I delegati sono simili al concetto di puntatori a funzione disponibili in altri linguaggi. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati agli oggetti e indipendenti dai tipi.</span><span class="sxs-lookup"><span data-stu-id="17901-106">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="17901-107">Nell'esempio seguente viene dichiarato e usato un tipo delegato denominato `Function`.</span><span class="sxs-lookup"><span data-stu-id="17901-107">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="17901-108">Un'istanza del tipo delegato `Function` può fare riferimento a qualsiasi metodo che accetta un argomento `double` e restituisce un valore `double`.</span><span class="sxs-lookup"><span data-stu-id="17901-108">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="17901-109">Il metodo `Apply` applica una funzione specificata agli elementi di un `double[]`, restituendo un `double[]` con i risultati.</span><span class="sxs-lookup"><span data-stu-id="17901-109">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="17901-110">Nel metodo `Main`, `Apply` viene usato per applicare a `double[]` tre funzioni differenti.</span><span class="sxs-lookup"><span data-stu-id="17901-110">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="17901-111">Un delegato può fare riferimento a un metodo statico, come `Square` o `Math.Sin` nell'esempio precedente, o a un metodo di istanza, come `m.Multiply` nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="17901-111">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="17901-112">Un delegato che fa riferimento a un metodo di istanza fa riferimento anche a un oggetto particolare. Quando il metodo di istanza viene richiamato tramite il delegato, l'oggetto diventa `this` nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="17901-112">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="17901-113">I delegati possono essere creati anche mediante funzioni anonime, ovvero "metodi inline" creati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="17901-113">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="17901-114">Le funzioni anonime possono vedere le variabili locali dei metodi circostanti.</span><span class="sxs-lookup"><span data-stu-id="17901-114">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="17901-115">Di conseguenza, il precedente esempio di moltiplicatore può essere scritto più facilmente senza usare una classe Multiplier:</span><span class="sxs-lookup"><span data-stu-id="17901-115">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="17901-116">Una proprietà interessante e utile di un delegato consiste nel fatto che non conosce o non prende in considerazione la classe del metodo a cui fa riferimento. Ciò che conta è che il metodo a cui un delegato fa riferimento abbia gli stessi parametri e restituisca lo stesso tipo del delegato in questione.</span><span class="sxs-lookup"><span data-stu-id="17901-116">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="17901-117">[Precedente](interfaces.md)
>[Successivo](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="17901-117">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
