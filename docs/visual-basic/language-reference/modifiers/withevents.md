---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583033"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="b58ee-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b58ee-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="b58ee-103">Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="b58ee-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="b58ee-104">Note</span><span class="sxs-lookup"><span data-stu-id="b58ee-104">Remarks</span></span>

<span data-ttu-id="b58ee-105">Quando una variabile viene definita utilizzando `WithEvents`, è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando la parola chiave `Handles`.</span><span class="sxs-lookup"><span data-stu-id="b58ee-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="b58ee-106">È possibile usare `WithEvents` solo a livello di classe o di modulo.</span><span class="sxs-lookup"><span data-stu-id="b58ee-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="b58ee-107">Ciò significa che il contesto di dichiarazione per una variabile di `WithEvents` deve essere una classe o un modulo e non può essere un file di origine, uno spazio dei nomi, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="b58ee-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="b58ee-108">Non è possibile usare `WithEvents` per un membro di struttura.</span><span class="sxs-lookup"><span data-stu-id="b58ee-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="b58ee-109">È possibile dichiarare solo singole variabili, non matrici, con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="b58ee-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="b58ee-110">Regole</span><span class="sxs-lookup"><span data-stu-id="b58ee-110">Rules</span></span>

<span data-ttu-id="b58ee-111">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="b58ee-111">**Element Types.**</span></span> <span data-ttu-id="b58ee-112">È necessario dichiarare le variabili di `WithEvents` come variabili oggetto in modo che possano accettare istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="b58ee-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="b58ee-113">Non è tuttavia possibile dichiararli come `Object`.</span><span class="sxs-lookup"><span data-stu-id="b58ee-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="b58ee-114">È necessario dichiararli come la classe specifica che può generare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="b58ee-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="b58ee-115">Il modificatore `WithEvents` può essere usato in questo contesto: [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="b58ee-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="b58ee-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b58ee-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="b58ee-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b58ee-117">See also</span></span>

- [<span data-ttu-id="b58ee-118">Handles</span><span class="sxs-lookup"><span data-stu-id="b58ee-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="b58ee-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b58ee-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="b58ee-120">Eventi</span><span class="sxs-lookup"><span data-stu-id="b58ee-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
