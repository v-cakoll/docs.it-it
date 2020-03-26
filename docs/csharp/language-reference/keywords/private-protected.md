---
title: private protected (informazioni di riferimento su C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 01a8b716ce87a63a50a92a25b2842f7bb12d4c9f
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134356"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="c27b9-102">private protected (informazioni di riferimento su C#)</span><span class="sxs-lookup"><span data-stu-id="c27b9-102">private protected (C# Reference)</span></span>

<span data-ttu-id="c27b9-103">La combinazione delle parole chiave `private protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="c27b9-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c27b9-104">Un membro protetto privato è accessibile per i tipi derivati dalla classe che lo contiene, ma solo all'interno dell'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c27b9-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="c27b9-105">Per un confronto di `private protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c27b9-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c27b9-106">Il modificatore di accesso `private protected` è valido in C# versione 7.2 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c27b9-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="c27b9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c27b9-107">Example</span></span>

<span data-ttu-id="c27b9-108">Un membro protetto privato di una classe base è accessibile dai tipi derivati nell'assembly che lo contiene solo se il tipo statico della variabile è il tipo della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c27b9-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="c27b9-109">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c27b9-109">For example, consider the following code segment:</span></span>  

```csharp
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="c27b9-110">Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="c27b9-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="c27b9-111">Il primo file contiene una classe base pubblica, `BaseClass`, e un tipo derivato, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="c27b9-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="c27b9-112">`BaseClass` è proprietaria di un membro protetto privato, `myValue`, a cui `DerivedClass1` prova ad accedere in due modi.</span><span class="sxs-lookup"><span data-stu-id="c27b9-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="c27b9-113">Il primo tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="c27b9-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="c27b9-114">Il tentativo di usarlo come membro ereditato in `DerivedClass1` avrà, tuttavia, esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c27b9-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="c27b9-115">Nel secondo file un tentativo di accedere a `myValue` come membro ereditato di `DerivedClass2` genererà un errore, perché è accessibile solo per i tipi derivati in Assembly1.</span><span class="sxs-lookup"><span data-stu-id="c27b9-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="c27b9-116">I membri struct non possono essere `private protected` perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="c27b9-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="c27b9-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c27b9-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="c27b9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c27b9-118">See also</span></span>

- [<span data-ttu-id="c27b9-119">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="c27b9-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c27b9-120">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="c27b9-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c27b9-121">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="c27b9-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c27b9-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="c27b9-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c27b9-123">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="c27b9-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c27b9-124">Modificatori</span><span class="sxs-lookup"><span data-stu-id="c27b9-124">Modifiers</span></span>](index.md)
- [<span data-ttu-id="c27b9-125">public</span><span class="sxs-lookup"><span data-stu-id="c27b9-125">public</span></span>](public.md)
- [<span data-ttu-id="c27b9-126">private</span><span class="sxs-lookup"><span data-stu-id="c27b9-126">private</span></span>](private.md)
- [<span data-ttu-id="c27b9-127">internal</span><span class="sxs-lookup"><span data-stu-id="c27b9-127">internal</span></span>](internal.md)
- <span data-ttu-id="c27b9-128">[Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c27b9-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
