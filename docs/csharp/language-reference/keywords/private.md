---
title: Parola chiave private (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 0c564f38940e993bdfb93af0ec995c684be0eeb7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43802717"
---
# <a name="private-c-reference"></a><span data-ttu-id="a9f8e-102">private (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a9f8e-102">private (C# Reference)</span></span>

<span data-ttu-id="a9f8e-103">La parola chiave `private` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="a9f8e-104">Questa pagina illustra l'accesso `private`.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-104">This page covers `private` access.</span></span> <span data-ttu-id="a9f8e-105">La parola chiave `private` fa anche parte del modificatore di accesso [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a9f8e-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="a9f8e-106">L'accesso privato è il livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="a9f8e-107">I membri privati sono accessibili solo all'interno del corpo della classe o dello struct in cui sono stati dichiarati, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a9f8e-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="a9f8e-108">Anche i tipi annidati dello stesso corpo possono accedere ai membri privati.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="a9f8e-109">Fare riferimento a un membro privato all'esterno della classe o dello struct in cui è stato dichiarato genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="a9f8e-110">Per un confronto di `private` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md) e [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a9f8e-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="a9f8e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9f8e-111">Example</span></span>

<span data-ttu-id="a9f8e-112">In questo esempio la classe `Employee` contiene due membri dati privati, `name` e `salary`.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="a9f8e-113">Essendo privati, i membri risulteranno accessibili solo ai metodi di membro.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="a9f8e-114">I metodi pubblici `GetName` e `Salary` vengono aggiunti per consentire il controllo dell'accesso ai membri privati.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="a9f8e-115">È possibile accedere al membro `name` tramite un metodo pubblico e al membro `salary` tramite una proprietà pubblica di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a9f8e-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="a9f8e-116">Per altre informazioni, vedere [Proprietà](../../programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="a9f8e-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="a9f8e-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a9f8e-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a9f8e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9f8e-118">See also</span></span>

- [<span data-ttu-id="a9f8e-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a9f8e-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="a9f8e-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a9f8e-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a9f8e-121">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a9f8e-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a9f8e-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="a9f8e-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a9f8e-123">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="a9f8e-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a9f8e-124">Modificatori</span><span class="sxs-lookup"><span data-stu-id="a9f8e-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="a9f8e-125">public</span><span class="sxs-lookup"><span data-stu-id="a9f8e-125">public</span></span>](public.md)
- [<span data-ttu-id="a9f8e-126">protected</span><span class="sxs-lookup"><span data-stu-id="a9f8e-126">protected</span></span>](protected.md)
- [<span data-ttu-id="a9f8e-127">internal</span><span class="sxs-lookup"><span data-stu-id="a9f8e-127">internal</span></span>](internal.md)