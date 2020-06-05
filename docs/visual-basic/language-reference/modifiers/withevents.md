---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386776"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="e9b79-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9b79-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="e9b79-103">Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="e9b79-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9b79-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="e9b79-104">Remarks</span></span>

<span data-ttu-id="e9b79-105">Quando una variabile viene definita tramite `WithEvents` , è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando la `Handles` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="e9b79-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="e9b79-106">È possibile usare `WithEvents` solo a livello di classe o di modulo.</span><span class="sxs-lookup"><span data-stu-id="e9b79-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="e9b79-107">Ciò significa che il contesto di dichiarazione per una `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, uno spazio dei nomi, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="e9b79-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="e9b79-108">Non è possibile usare `WithEvents` in un membro di struttura.</span><span class="sxs-lookup"><span data-stu-id="e9b79-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="e9b79-109">È possibile dichiarare solo singole variabili, non matrici, con `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="e9b79-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="e9b79-110">Regole</span><span class="sxs-lookup"><span data-stu-id="e9b79-110">Rules</span></span>

<span data-ttu-id="e9b79-111">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="e9b79-111">**Element Types.**</span></span> <span data-ttu-id="e9b79-112">È necessario dichiarare le `WithEvents` variabili come variabili oggetto in modo che possano accettare istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="e9b79-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="e9b79-113">Tuttavia, non è possibile dichiararli come `Object` .</span><span class="sxs-lookup"><span data-stu-id="e9b79-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="e9b79-114">È necessario dichiararli come la classe specifica che può generare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="e9b79-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="e9b79-115">Il `WithEvents` modificatore può essere usato in questo contesto: [istruzione Dim](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e9b79-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="e9b79-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9b79-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="e9b79-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b79-117">See also</span></span>

- [<span data-ttu-id="e9b79-118">Selettori</span><span class="sxs-lookup"><span data-stu-id="e9b79-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="e9b79-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e9b79-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="e9b79-120">Events</span><span class="sxs-lookup"><span data-stu-id="e9b79-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
