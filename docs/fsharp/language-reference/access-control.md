---
title: Controllo di accesso (F#)
description: 'Informazioni su come controllare l''accesso a elementi di programmazione, ad esempio tipi, metodi e funzioni, il linguaggio di programmazione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="4d0d4-104">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="4d0d4-104">Access Control</span></span>

<span data-ttu-id="4d0d4-105">*Controllo di accesso* fa riferimento a una dichiarazione che i client possono utilizzare alcuni elementi di programma, ad esempio tipi, metodi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="4d0d4-106">Nozioni di base del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="4d0d4-106">Basics of Access Control</span></span>
<span data-ttu-id="4d0d4-107">In F #, identificatori del controllo di accesso `public`, `internal`, e `private` può essere applicato ai moduli, tipi, metodi, le definizioni di valore, funzioni, proprietà e i campi espliciti.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="4d0d4-108">`public`indica che l'entità sia accessibile da tutti i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="4d0d4-109">`internal`indica che l'entità è possibile accedere solo dallo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="4d0d4-110">`private`indica che l'entità è possibile accedere solo dal tipo o modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="4d0d4-111">L'identificatore di accesso `protected` non viene usato in F #, ma è accettabile se si utilizzano tipi creati in linguaggi che supportano `protected` accesso.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="4d0d4-112">Pertanto, se si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="4d0d4-113">In generale, l'identificatore è posizionato davanti al nome dell'entità, tranne quando una `mutable` o `inline` identificatore viene usato, che appare dopo l'identificatore del controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="4d0d4-114">Se viene utilizzato alcun identificatore di accesso, il valore predefinito è `public`, ad eccezione di `let` binding in un tipo, che sono sempre `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="4d0d4-115">Le firme in F # è un altro meccanismo per controllare l'accesso agli elementi del programma F #.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="4d0d4-116">Le firme non sono necessari per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-116">Signatures are not required for access control.</span></span> <span data-ttu-id="4d0d4-117">Per altre informazioni, vedere [Firme](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="4d0d4-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="4d0d4-118">Regole per il controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="4d0d4-118">Rules for Access Control</span></span>
<span data-ttu-id="4d0d4-119">Controllo di accesso è soggetto alle seguenti regole:</span><span class="sxs-lookup"><span data-stu-id="4d0d4-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="4d0d4-120">Le dichiarazioni di ereditarietà (ovvero, l'utilizzo di `inherit` per specificare una classe base per una classe), le dichiarazioni (ovvero, la specifica che una classe implementa un'interfaccia) di interfaccia e l'astrazione membri hanno sempre la stessa accessibilità del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="4d0d4-121">Pertanto, un identificatore di controllo di accesso può essere usato in questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="4d0d4-122">Singoli case in un'unione discriminata non possono contenere i propri modificatori di controllo di accesso separati dal tipo di unione.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="4d0d4-123">I singoli campi di un tipo di record non possono contenere i propri modificatori di controllo di accesso separati dal tipo di record.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="4d0d4-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d0d4-124">Example</span></span>
<span data-ttu-id="4d0d4-125">Il codice seguente viene illustrato l'utilizzo di identificatori di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="4d0d4-126">Sono disponibili due file del progetto, `Module1.fs` e `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="4d0d4-127">Ogni file in modo implicito è un modulo.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-127">Each file is implicitly a module.</span></span> <span data-ttu-id="4d0d4-128">Pertanto, sono presenti due moduli, `Module1` e `Module2`.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="4d0d4-129">Un tipo privato e un tipo interno sono definiti nel `Module1`.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="4d0d4-130">Il tipo privato non sono accessibili da `Module2`, ma è di tipo interno.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="4d0d4-131">Il codice seguente controlla l'accessibilità di tipi creati in `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="4d0d4-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="4d0d4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d0d4-132">See Also</span></span>
[<span data-ttu-id="4d0d4-133">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4d0d4-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4d0d4-134">Firme</span><span class="sxs-lookup"><span data-stu-id="4d0d4-134">Signatures</span></span>](signatures.md)
