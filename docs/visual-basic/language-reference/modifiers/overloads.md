---
title: Overload
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: bd0931cab520f8580c0d7473a44e350752e287bb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392106"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="f6639-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6639-102">Overloads (Visual Basic)</span></span>

<span data-ttu-id="f6639-103">Specifica che una proprietà o una routine ridichiara una o più proprietà o routine esistenti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f6639-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6639-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6639-104">Remarks</span></span>

<span data-ttu-id="f6639-105">L' *Overload* è la pratica di fornire più di una definizione per un nome di proprietà o di routine specifico nello stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="f6639-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="f6639-106">La ridichiarazione di una proprietà o di una routine con una firma diversa viene talvolta chiamata *nascosta dalla firma*.</span><span class="sxs-lookup"><span data-stu-id="f6639-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>

## <a name="rules"></a><span data-ttu-id="f6639-107">Regole</span><span class="sxs-lookup"><span data-stu-id="f6639-107">Rules</span></span>

- <span data-ttu-id="f6639-108">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="f6639-108">**Declaration Context.**</span></span> <span data-ttu-id="f6639-109">È possibile utilizzare `Overloads` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="f6639-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="f6639-110">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="f6639-110">**Combined Modifiers.**</span></span> <span data-ttu-id="f6639-111">Non è possibile specificare `Overloads` insieme a [Shadows](shadows.md) nella stessa dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="f6639-111">You cannot specify `Overloads` together with [Shadows](shadows.md) in the same procedure declaration.</span></span>

- <span data-ttu-id="f6639-112">**Differenze necessarie.**</span><span class="sxs-lookup"><span data-stu-id="f6639-112">**Required Differences.**</span></span> <span data-ttu-id="f6639-113">La *firma* in questa dichiarazione deve essere diversa dalla firma di ogni proprietà o routine che viene sovraccaricata.</span><span class="sxs-lookup"><span data-stu-id="f6639-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="f6639-114">La firma comprende il nome della proprietà o della routine e gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6639-114">The signature comprises the property or procedure name together with the following:</span></span>

  - <span data-ttu-id="f6639-115">numero dei parametri</span><span class="sxs-lookup"><span data-stu-id="f6639-115">the number of parameters</span></span>

  - <span data-ttu-id="f6639-116">ordine dei parametri</span><span class="sxs-lookup"><span data-stu-id="f6639-116">the order of the parameters</span></span>

  - <span data-ttu-id="f6639-117">tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="f6639-117">the data types of the parameters</span></span>

  - <span data-ttu-id="f6639-118">numero dei parametri di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="f6639-118">the number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="f6639-119">tipo restituito (solo per una routine di operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="f6639-119">the return type (only for a conversion operator procedure)</span></span>

  <span data-ttu-id="f6639-120">Tutti gli overload devono avere lo stesso nome, ma ognuno deve essere diverso da tutti gli altri per uno o più elementi tra quelli elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f6639-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="f6639-121">Questo consente al compilatore di distinguere la versione da usare quando il codice chiama la proprietà o la routine.</span><span class="sxs-lookup"><span data-stu-id="f6639-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>

- <span data-ttu-id="f6639-122">**Differenze non consentite.**</span><span class="sxs-lookup"><span data-stu-id="f6639-122">**Disallowed Differences.**</span></span> <span data-ttu-id="f6639-123">Poiché gli elementi riportati di seguito non fanno parte della firma, la relativa modifica non è valida per l'overload di una proprietà o di una routine:</span><span class="sxs-lookup"><span data-stu-id="f6639-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>

  - <span data-ttu-id="f6639-124">la capacità di restituire un valore (per una routine)</span><span class="sxs-lookup"><span data-stu-id="f6639-124">whether or not it returns a value (for a procedure)</span></span>

  - <span data-ttu-id="f6639-125">il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="f6639-125">the data type of the return value (except for a conversion operator)</span></span>

  - <span data-ttu-id="f6639-126">i nomi dei parametri o dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f6639-126">the names of the parameters or type parameters</span></span>

  - <span data-ttu-id="f6639-127">i vincoli definiti sui parametri di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="f6639-127">the constraints on the type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="f6639-128">le parole chiave di modificatori di parametro (ad esempio `ByRef` o `Optional`)</span><span class="sxs-lookup"><span data-stu-id="f6639-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>

  - <span data-ttu-id="f6639-129">e parole chiave di modificatori di proprietà o di routine (ad esempio `Public` o `Shared`)</span><span class="sxs-lookup"><span data-stu-id="f6639-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>

- <span data-ttu-id="f6639-130">**Modificatore facoltativo.**</span><span class="sxs-lookup"><span data-stu-id="f6639-130">**Optional Modifier.**</span></span> <span data-ttu-id="f6639-131">Non è necessario usare il `Overloads` modificatore quando si definiscono più proprietà o routine di overload nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="f6639-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="f6639-132">Se tuttavia si usa `Overloads` in una dichiarazione, è necessario usarlo in tutte.</span><span class="sxs-lookup"><span data-stu-id="f6639-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>

- <span data-ttu-id="f6639-133">**Ombreggiatura e overload.**</span><span class="sxs-lookup"><span data-stu-id="f6639-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="f6639-134">`Overloads`può anche essere usato per nascondere un membro esistente o un set di membri di overload in una classe base.</span><span class="sxs-lookup"><span data-stu-id="f6639-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="f6639-135">Quando si usa `Overloads` a questo scopo, è necessario dichiarare la proprietà o il metodo con lo stesso nome e lo stesso elenco di parametri del membro della classe base, senza specificare la parola chiave `Shadows`.</span><span class="sxs-lookup"><span data-stu-id="f6639-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>

<span data-ttu-id="f6639-136">Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="f6639-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="f6639-137">Il modificatore `Overloads` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6639-137">The `Overloads` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="f6639-138">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f6639-138">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="f6639-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f6639-139">Operator Statement</span></span>](../statements/operator-statement.md)

- [<span data-ttu-id="f6639-140">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f6639-140">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="f6639-141">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f6639-141">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="f6639-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6639-142">See also</span></span>

- [<span data-ttu-id="f6639-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="f6639-143">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="f6639-144">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="f6639-144">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="f6639-145">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6639-145">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="f6639-146">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f6639-146">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="f6639-147">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="f6639-147">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
