---
title: Controllo di accesso
description: Informazioni su come controllare l'accesso agli elementi di programmazione, ad esempio tipi, metodi e funzioni, nel F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: ed77a09cf87aabf9a4134276e89e84aa42abd3c3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629963"
---
# <a name="access-control"></a><span data-ttu-id="8a163-103">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="8a163-103">Access Control</span></span>

<span data-ttu-id="8a163-104">Il *controllo di accesso* si riferisce alla dichiarazione dei client che possono usare determinati elementi di programma, ad esempio tipi, metodi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="8a163-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="8a163-105">Nozioni di base sul controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="8a163-105">Basics of Access Control</span></span>

<span data-ttu-id="8a163-106">In F#gli identificatori `public`di controllo di accesso `internal`, e `private` possono essere applicati a moduli, tipi, metodi, definizioni di valori, funzioni, proprietà e campi espliciti.</span><span class="sxs-lookup"><span data-stu-id="8a163-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="8a163-107">`public`indica che l'entità può accedere a tutti i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="8a163-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="8a163-108">`internal`indica che è possibile accedere all'entità solo dallo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="8a163-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="8a163-109">`private`indica che è possibile accedere all'entità solo dal tipo o dal modulo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="8a163-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="8a163-110">L'identificatore `protected` di accesso non viene usato F#in, sebbene sia accettabile se si usano tipi creati in linguaggi che supportano `protected` l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="8a163-111">Se pertanto si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e dei relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="8a163-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="8a163-112">In generale, l'identificatore viene inserito davanti al nome dell'entità, tranne quando viene usato un identificatore `mutable` o `inline` , che viene visualizzato dopo l'identificatore di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="8a163-113">Se non viene usato alcun identificatore di accesso, il `public`valore predefinito è `let` , ad eccezione delle associazioni in un tipo, `private` che sono sempre di tipo.</span><span class="sxs-lookup"><span data-stu-id="8a163-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="8a163-114">Le firme F# in forniscono un altro meccanismo per controllare F# l'accesso agli elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="8a163-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="8a163-115">Le firme non sono necessarie per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-115">Signatures are not required for access control.</span></span> <span data-ttu-id="8a163-116">Per altre informazioni, vedere [Firme](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="8a163-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="8a163-117">Regole per il controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="8a163-117">Rules for Access Control</span></span>

<span data-ttu-id="8a163-118">Il controllo di accesso è soggetto alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a163-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="8a163-119">Dichiarazioni di ereditarietà (ovvero l'uso di `inherit` per specificare una classe di base per una classe), dichiarazioni di interfaccia (ovvero specificando che una classe implementa un'interfaccia) e i membri astratti hanno sempre la stessa accessibilità del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="8a163-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="8a163-120">Pertanto, non è possibile utilizzare un identificatore di controllo di accesso in questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="8a163-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="8a163-121">L'accessibilità per i singoli casi in un'unione discriminata è determinata dall'accessibilità dell'unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="8a163-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="8a163-122">Ovvero un particolare case di Unione non è meno accessibile dell'Unione stessa.</span><span class="sxs-lookup"><span data-stu-id="8a163-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="8a163-123">L'accessibilità per i singoli campi di un tipo di record non può essere determinata dall'accessibilità del record stesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="8a163-124">Ovvero, una particolare etichetta di record non è meno accessibile del record stesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="8a163-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a163-125">Example</span></span>

<span data-ttu-id="8a163-126">Il codice seguente illustra l'uso degli identificatori di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="8a163-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="8a163-127">Il progetto contiene due file, `Module1.fs` e. `Module2.fs`</span><span class="sxs-lookup"><span data-stu-id="8a163-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="8a163-128">Ogni file è implicitamente un modulo.</span><span class="sxs-lookup"><span data-stu-id="8a163-128">Each file is implicitly a module.</span></span> <span data-ttu-id="8a163-129">Sono pertanto presenti due moduli, `Module1` e. `Module2`</span><span class="sxs-lookup"><span data-stu-id="8a163-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="8a163-130">In `Module1`sono definiti un tipo privato e un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="8a163-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="8a163-131">Il tipo privato non è accessibile da `Module2`, ma il tipo interno può essere.</span><span class="sxs-lookup"><span data-stu-id="8a163-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="8a163-132">Il codice seguente verifica l'accessibilità dei tipi creati in `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="8a163-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="8a163-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a163-133">See also</span></span>

- [<span data-ttu-id="8a163-134">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="8a163-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8a163-135">Firme</span><span class="sxs-lookup"><span data-stu-id="8a163-135">Signatures</span></span>](signatures.md)
