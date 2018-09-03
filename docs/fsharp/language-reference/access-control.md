---
title: Controllo di accesso (F#)
description: "Informazioni su come controllare l'accesso agli elementi di programmazione, ad esempio i tipi, metodi e funzioni, il linguaggio di programmazione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 6b13ac03d2a4a6c53b53d4c790760f5d51b334ee
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43456344"
---
# <a name="access-control"></a><span data-ttu-id="6e3ee-103">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="6e3ee-103">Access Control</span></span>

<span data-ttu-id="6e3ee-104">*Controllo di accesso* fa riferimento alla dichiarazione di client in cui è possono usare determinati elementi di programma, ad esempio i tipi, metodi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="6e3ee-105">Nozioni di base del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="6e3ee-105">Basics of Access Control</span></span>
<span data-ttu-id="6e3ee-106">In F #, identificatori del controllo di accesso `public`, `internal`, e `private` è applicabile ai moduli, tipi, metodi, le definizioni di valore, funzioni, proprietà e i campi espliciti.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="6e3ee-107">`public` indica che l'entità sia accessibile da tutti i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="6e3ee-108">`internal` indica che l'entità sia accessibile solo dallo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="6e3ee-109">`private` indica che l'entità sia accessibile solo dal tipo o modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

>[!NOTE] 
<span data-ttu-id="6e3ee-110">L'identificatore di accesso `protected` non viene usato in F #, anche se è accettabile se si utilizzano tipi creati in linguaggi che supportano `protected` accesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="6e3ee-111">Pertanto, se si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="6e3ee-112">In generale, l'identificatore viene inserito davanti al nome dell'entità, tranne quando un `mutable` o `inline` identificatore viene usato, che appare dopo l'identificatore del controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="6e3ee-113">Se non viene usato alcun identificatore di accesso, il valore predefinito è `public`, ad eccezione di `let` associazioni in un tipo, che sono sempre `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="6e3ee-114">Le firme in F # forniscono un altro meccanismo per controllare l'accesso agli elementi del programma F #.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="6e3ee-115">Le firme non sono necessarie per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-115">Signatures are not required for access control.</span></span> <span data-ttu-id="6e3ee-116">Per altre informazioni, vedere [Firme](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="6e3ee-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="6e3ee-117">Regole di controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="6e3ee-117">Rules for Access Control</span></span>
<span data-ttu-id="6e3ee-118">Controllo di accesso è soggetto alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e3ee-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="6e3ee-119">Le dichiarazioni di ereditarietà (vale a dire l'uso di `inherit` per specificare una classe base per una classe), le dichiarazioni (ovvero, la specifica che una classe implementa un'interfaccia) di interfaccia e l'astrazione membri hanno sempre la stessa accessibilità del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="6e3ee-120">Pertanto, un identificatore di controllo di accesso non può essere utilizzato su questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="6e3ee-121">Accessibilità per singoli case in un'unione discriminata è determinato dall'accessibilità dell'unione discriminata stesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="6e3ee-122">Un particolare case di unione è l'unione stessa non è meno accessibile.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="6e3ee-123">Accessibilità per i singoli campi di un tipo di record non è determinata dall'accessibilità del record stesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="6e3ee-124">Vale a dire, un'etichetta di record specifico è non meno accessibile il record stesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="6e3ee-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e3ee-125">Example</span></span>
<span data-ttu-id="6e3ee-126">Il codice seguente viene illustrato l'utilizzo di identificatori di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="6e3ee-127">Sono disponibili due file nel progetto `Module1.fs` e `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="6e3ee-128">Ogni file in modo implicito è un modulo.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-128">Each file is implicitly a module.</span></span> <span data-ttu-id="6e3ee-129">Pertanto, sono presenti due moduli `Module1` e `Module2`.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="6e3ee-130">Un tipo privato e un tipo interno sono definiti nel `Module1`.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="6e3ee-131">Il tipo privato non è accessibile da `Module2`, ma è di tipo interno.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="6e3ee-132">Il codice seguente verifica l'accessibilità dei tipi creati `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="6e3ee-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="6e3ee-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e3ee-133">See Also</span></span>
[<span data-ttu-id="6e3ee-134">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="6e3ee-134">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6e3ee-135">Firme</span><span class="sxs-lookup"><span data-stu-id="6e3ee-135">Signatures</span></span>](signatures.md)
