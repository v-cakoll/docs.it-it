---
title: Espressioni lambda tipizzate in modo implicito
description: Informazioni sul motivo per cui non è possibile usare una dichiarazione di variabile tipizzata in modo implicito per dichiarare un'espressione lambda.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: cf16bb4d9ed27f536ae163284f36a0f305877139
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713880"
---
# <a name="implicitly-typed-lambda-expressions"></a><span data-ttu-id="d2a3c-103">Espressioni lambda tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="d2a3c-103">Implicitly typed lambda expressions</span></span>

<span data-ttu-id="d2a3c-104">Per dichiarare un'espressione lambda non è consentito dichiarare una variabile tipizzata in modo implicito,</span><span class="sxs-lookup"><span data-stu-id="d2a3c-104">You can't use an implicitly typed variable declaration to declare a lambda expression.</span></span>
<span data-ttu-id="d2a3c-105">poiché causerebbe un problema di logica circolare per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-105">It creates a circular logic problem for the compiler.</span></span> <span data-ttu-id="d2a3c-106">La dichiarazione di `var` richiede al compilatore di determinare il tipo della variabile dal tipo dell'espressione a destra dell'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-106">The `var` declaration tells the compiler to figure out the type of the variable from the type of expression on the right hand side of the assignment operator.</span></span> <span data-ttu-id="d2a3c-107">Un'espressione lambda non ha un tipo in fase di compilazione, ma può essere convertita in un qualsiasi tipo di delegato o di espressione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-107">A lambda expression does not have a compile time type, but is convertible to any matching delegate or expression type.</span></span> <span data-ttu-id="d2a3c-108">Quando si assegna un'espressione lambda a una variabile di tipo delegato o espressione, si indica al compilatore di tentare di convertire l'espressione lambda in un'espressione o in un delegato che corrisponda alla firma della variabile di destinazione dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-108">When you assign a lambda expression to a variable of a delegate or expression type, you tell the compiler to try and convert the lambda expression into an expression or delegate that matches the signature of the 'assigned to' variable.</span></span> <span data-ttu-id="d2a3c-109">Il compilatore deve fare in modo che il tipo dell'elemento a destra dell'operatore di assegnazione corrisponda al tipo a sinistra di tale operatore.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-109">The compiler must try to make the thing on the right hand side of the assignment match the type on the left hand side of the assignment.</span></span> 

<span data-ttu-id="d2a3c-110">Nessuno dei lati dell'assegnazione può indicare al compilatore di esaminare l'oggetto del lato opposto dell'operatore di assegnazione per verificare se il tipo di tale oggetto corrisponde al proprio.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-110">Both sides of the assignment can't be telling the compiler to look at the object on the other side of the assignment operator and see if my type matches.</span></span>

<span data-ttu-id="d2a3c-111">È possibile ottenere altre informazioni sui motivi per cui C# il linguaggio specifica tale comportamento leggendo [questo articolo](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (Download PDF).</span><span class="sxs-lookup"><span data-stu-id="d2a3c-111">You can get even more details on why the C# language specifies that behavior by reading [this article](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF download).</span></span>
