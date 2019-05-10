---
title: Overloads (Visual Basic)
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
ms.openlocfilehash: ab8660ff0cf02956e760132f5aad69e359913950
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661090"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="2cd06-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cd06-102">Overloads (Visual Basic)</span></span>
<span data-ttu-id="2cd06-103">Specifica che una proprietà o una routine ridichiara una o più proprietà o routine esistenti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2cd06-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cd06-104">Note</span><span class="sxs-lookup"><span data-stu-id="2cd06-104">Remarks</span></span>  
 <span data-ttu-id="2cd06-105">*L'overload* è la pratica di fornire più di una definizione per un determinato nome di proprietà o routine nello stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="2cd06-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="2cd06-106">La ridichiarazione di una proprietà o routine con una firma diversa viene talvolta chiamata *nascondere con la firma*.</span><span class="sxs-lookup"><span data-stu-id="2cd06-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2cd06-107">Regole</span><span class="sxs-lookup"><span data-stu-id="2cd06-107">Rules</span></span>  
  
- <span data-ttu-id="2cd06-108">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-108">**Declaration Context.**</span></span> <span data-ttu-id="2cd06-109">È possibile usare `Overloads` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="2cd06-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>  
  
- <span data-ttu-id="2cd06-110">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-110">**Combined Modifiers.**</span></span> <span data-ttu-id="2cd06-111">Non è possibile specificare `Overloads` assieme [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) nella stessa dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="2cd06-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>  
  
- <span data-ttu-id="2cd06-112">**Differenze necessarie.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-112">**Required Differences.**</span></span> <span data-ttu-id="2cd06-113">Il *firma* in questa dichiarazione deve essere diverso dalla firma di tutte le proprietà o routine che esegue l'overload.</span><span class="sxs-lookup"><span data-stu-id="2cd06-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="2cd06-114">La firma comprende il nome della proprietà o della routine e gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd06-114">The signature comprises the property or procedure name together with the following:</span></span>  
  
    - <span data-ttu-id="2cd06-115">numero dei parametri</span><span class="sxs-lookup"><span data-stu-id="2cd06-115">the number of parameters</span></span>  
  
    - <span data-ttu-id="2cd06-116">ordine dei parametri</span><span class="sxs-lookup"><span data-stu-id="2cd06-116">the order of the parameters</span></span>  
  
    - <span data-ttu-id="2cd06-117">tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="2cd06-117">the data types of the parameters</span></span>  
  
    - <span data-ttu-id="2cd06-118">numero dei parametri di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="2cd06-118">the number of type parameters (for a generic procedure)</span></span>  
  
    - <span data-ttu-id="2cd06-119">tipo restituito (solo per una routine di operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="2cd06-119">the return type (only for a conversion operator procedure)</span></span>  
  
     <span data-ttu-id="2cd06-120">Tutti gli overload devono avere lo stesso nome, ma ognuno deve essere diverso da tutti gli altri per uno o più elementi tra quelli elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2cd06-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="2cd06-121">Questo consente al compilatore di distinguere la versione da usare quando il codice chiama la proprietà o la routine.</span><span class="sxs-lookup"><span data-stu-id="2cd06-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>  
  
- <span data-ttu-id="2cd06-122">**Differenze non consentite.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-122">**Disallowed Differences.**</span></span> <span data-ttu-id="2cd06-123">Poiché gli elementi riportati di seguito non fanno parte della firma, la relativa modifica non è valida per l'overload di una proprietà o di una routine:</span><span class="sxs-lookup"><span data-stu-id="2cd06-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>  
  
    - <span data-ttu-id="2cd06-124">la capacità di restituire un valore (per una routine)</span><span class="sxs-lookup"><span data-stu-id="2cd06-124">whether or not it returns a value (for a procedure)</span></span>  
  
    - <span data-ttu-id="2cd06-125">il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="2cd06-125">the data type of the return value (except for a conversion operator)</span></span>  
  
    - <span data-ttu-id="2cd06-126">i nomi dei parametri o dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2cd06-126">the names of the parameters or type parameters</span></span>  
  
    - <span data-ttu-id="2cd06-127">i vincoli definiti sui parametri di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="2cd06-127">the constraints on the type parameters (for a generic procedure)</span></span>  
  
    - <span data-ttu-id="2cd06-128">le parole chiave di modificatori di parametro (ad esempio `ByRef` o `Optional`)</span><span class="sxs-lookup"><span data-stu-id="2cd06-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>  
  
    - <span data-ttu-id="2cd06-129">e parole chiave di modificatori di proprietà o di routine (ad esempio `Public` o `Shared`)</span><span class="sxs-lookup"><span data-stu-id="2cd06-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>  
  
- <span data-ttu-id="2cd06-130">**Modificatore facoltativo.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-130">**Optional Modifier.**</span></span> <span data-ttu-id="2cd06-131">Non è necessario usare il modificatore `Overloads` quando si definiscono più proprietà o routine in overload nella medesima classe.</span><span class="sxs-lookup"><span data-stu-id="2cd06-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="2cd06-132">Se tuttavia si usa `Overloads` in una dichiarazione, è necessario usarlo in tutte.</span><span class="sxs-lookup"><span data-stu-id="2cd06-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>  
  
- <span data-ttu-id="2cd06-133">**Shadowing e overload.**</span><span class="sxs-lookup"><span data-stu-id="2cd06-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="2cd06-134">`Overloads` è anche utilizzabile per nascondere un membro esistente o un set di membri in overload, in una classe base.</span><span class="sxs-lookup"><span data-stu-id="2cd06-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="2cd06-135">Quando si usa `Overloads` a questo scopo, è necessario dichiarare la proprietà o il metodo con lo stesso nome e lo stesso elenco di parametri del membro della classe base, senza specificare la parola chiave `Shadows`.</span><span class="sxs-lookup"><span data-stu-id="2cd06-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>  
  
 <span data-ttu-id="2cd06-136">Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="2cd06-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="2cd06-137">Il modificatore `Overloads` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd06-137">The `Overloads` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="2cd06-138">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="2cd06-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="2cd06-139">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="2cd06-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="2cd06-140">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="2cd06-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="2cd06-141">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="2cd06-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2cd06-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cd06-142">See also</span></span>

- [<span data-ttu-id="2cd06-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="2cd06-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="2cd06-144">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="2cd06-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="2cd06-145">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2cd06-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="2cd06-146">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="2cd06-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="2cd06-147">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="2cd06-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
