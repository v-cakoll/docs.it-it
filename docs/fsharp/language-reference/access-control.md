---
title: Controllo di accesso (F#)
description: "Informazioni su come controllare l'accesso a elementi di programmazione, ad esempio tipi, metodi e funzioni, il linguaggio di programmazione F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fee5f719904b61c3082d56f73448defdea39f472
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="access-control"></a><span data-ttu-id="075de-103">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="075de-103">Access Control</span></span>

<span data-ttu-id="075de-104">*Il controllo degli accessi* fa riferimento alla dichiarazione quali client possono utilizzare alcuni elementi di programma, ad esempio i tipi, metodi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="075de-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="075de-105">Nozioni di base del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="075de-105">Basics of Access Control</span></span>
<span data-ttu-id="075de-106">In F #, identificatori del controllo di accesso `public`, `internal`, e `private` può essere applicato ai moduli, tipi, metodi, le definizioni di valore, funzioni, proprietà e i campi espliciti.</span><span class="sxs-lookup"><span data-stu-id="075de-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="075de-107">`public` indica che l'entità sia accessibile da tutti i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="075de-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="075de-108">`internal` indica che l'entità sia accessibile solo dallo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="075de-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="075de-109">`private` indica che l'entità sia accessibile solo dal tipo o modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="075de-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="075de-110">L'identificatore di accesso `protected` non viene usato in F #, ma è accettabile se si utilizzano tipi creati in linguaggi che supportano `protected` accesso.</span><span class="sxs-lookup"><span data-stu-id="075de-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="075de-111">Pertanto, se si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="075de-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="075de-112">In generale, l'identificatore è posizionato davanti al nome dell'entità, tranne quando una `mutable` o `inline` identificatore viene usato, che appare dopo l'identificatore del controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="075de-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="075de-113">Se viene utilizzato alcun identificatore di accesso, il valore predefinito è `public`, ad eccezione di `let` binding in un tipo, che sono sempre `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="075de-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="075de-114">Le firme in F # è un altro meccanismo per controllare l'accesso agli elementi del programma F #.</span><span class="sxs-lookup"><span data-stu-id="075de-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="075de-115">Le firme non sono necessari per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="075de-115">Signatures are not required for access control.</span></span> <span data-ttu-id="075de-116">Per altre informazioni, vedere [Firme](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="075de-116">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="075de-117">Regole per il controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="075de-117">Rules for Access Control</span></span>
<span data-ttu-id="075de-118">Controllo di accesso è soggetto alle seguenti regole:</span><span class="sxs-lookup"><span data-stu-id="075de-118">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="075de-119">Le dichiarazioni di ereditarietà (ovvero, l'utilizzo di `inherit` per specificare una classe base per una classe), le dichiarazioni (ovvero, la specifica che una classe implementa un'interfaccia) di interfaccia e l'astrazione membri hanno sempre la stessa accessibilità del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="075de-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="075de-120">Pertanto, un identificatore di controllo di accesso può essere usato in questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="075de-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="075de-121">Singoli case in un'unione discriminata non possono contenere i propri modificatori di controllo di accesso separati dal tipo di unione.</span><span class="sxs-lookup"><span data-stu-id="075de-121">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="075de-122">I singoli campi di un tipo di record non possono contenere i propri modificatori di controllo di accesso separati dal tipo di record.</span><span class="sxs-lookup"><span data-stu-id="075de-122">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="075de-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="075de-123">Example</span></span>
<span data-ttu-id="075de-124">Il codice seguente viene illustrato l'utilizzo di identificatori di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="075de-124">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="075de-125">Sono disponibili due file del progetto, `Module1.fs` e `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="075de-125">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="075de-126">Ogni file in modo implicito è un modulo.</span><span class="sxs-lookup"><span data-stu-id="075de-126">Each file is implicitly a module.</span></span> <span data-ttu-id="075de-127">Pertanto, sono presenti due moduli, `Module1` e `Module2`.</span><span class="sxs-lookup"><span data-stu-id="075de-127">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="075de-128">Un tipo privato e un tipo interno sono definiti nel `Module1`.</span><span class="sxs-lookup"><span data-stu-id="075de-128">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="075de-129">Il tipo privato non sono accessibili da `Module2`, ma è di tipo interno.</span><span class="sxs-lookup"><span data-stu-id="075de-129">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="075de-130">Il codice seguente controlla l'accessibilità di tipi creati in `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="075de-130">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="075de-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="075de-131">See Also</span></span>
[<span data-ttu-id="075de-132">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="075de-132">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="075de-133">Firme</span><span class="sxs-lookup"><span data-stu-id="075de-133">Signatures</span></span>](signatures.md)
