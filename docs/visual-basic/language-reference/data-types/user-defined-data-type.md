---
title: Tipo di dati definito dall'utente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 76073037dcaac0e87bc8a352f3b438332d11d881
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630137"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="8e141-102">Tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="8e141-102">User-Defined Data Type</span></span>

<span data-ttu-id="8e141-103">Include i dati in un formato definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8e141-103">Holds data in a format you define.</span></span> <span data-ttu-id="8e141-104">L' `Structure` istruzione definisce il formato.</span><span class="sxs-lookup"><span data-stu-id="8e141-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="8e141-105">Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="8e141-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="8e141-106">La versione corrente espande il tipo definito dall'utente a una *struttura*.</span><span class="sxs-lookup"><span data-stu-id="8e141-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="8e141-107">Una struttura è una concatenazione di uno o più *membri* di diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="8e141-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="8e141-108">Visual Basic considera una struttura come una singola unità, sebbene sia anche possibile accedere singolarmente ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="8e141-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e141-109">Note</span><span class="sxs-lookup"><span data-stu-id="8e141-109">Remarks</span></span>

<span data-ttu-id="8e141-110">Definire e usare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità o quando nessuno dei tipi di dati elementari soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="8e141-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="8e141-111">Il valore predefinito di un tipo di dati della struttura è costituito dalla combinazione dei valori predefiniti di ognuno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="8e141-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="8e141-112">Formato della dichiarazione</span><span class="sxs-lookup"><span data-stu-id="8e141-112">Declaration Format</span></span>

<span data-ttu-id="8e141-113">Una dichiarazione di struttura inizia con l' [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) e termina con `End Structure` l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8e141-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="8e141-114">L' `Structure` istruzione fornisce il nome della struttura, che è anche l'identificatore del tipo di dati che la struttura sta definendo.</span><span class="sxs-lookup"><span data-stu-id="8e141-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="8e141-115">Altre parti del codice possono usare questo identificatore per dichiarare variabili, parametri e valori restituiti della funzione in modo che siano del tipo di dati della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e141-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="8e141-116">Le dichiarazioni tra le `Structure` istruzioni e `End Structure` definiscono i membri della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e141-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="8e141-117">Livelli di accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="8e141-117">Member Access Levels</span></span>

<span data-ttu-id="8e141-118">È necessario dichiarare ogni membro usando un' [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md)o [private](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="8e141-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="8e141-119">Se si usa un' `Dim` istruzione, il livello di accesso predefinito è public.</span><span class="sxs-lookup"><span data-stu-id="8e141-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="8e141-120">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="8e141-120">Programming Tips</span></span>

- <span data-ttu-id="8e141-121">**Consumo di memoria.**</span><span class="sxs-lookup"><span data-stu-id="8e141-121">**Memory Consumption.**</span></span> <span data-ttu-id="8e141-122">Come per tutti i tipi di dati compositi, non è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura aggiungendo le allocazioni di archiviazione nominale dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="8e141-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="8e141-123">Inoltre, non è possibile presupporre in modo sicuro che l'ordine di archiviazione in memoria sia uguale all'ordine di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="8e141-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="8e141-124">Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare l' <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo `Structure` all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8e141-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="8e141-125">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="8e141-125">**Interop Considerations.**</span></span> <span data-ttu-id="8e141-126">Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="8e141-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="8e141-127">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="8e141-127">**Widening.**</span></span> <span data-ttu-id="8e141-128">Non viene eseguita alcuna conversione automatica da o verso qualsiasi tipo di dati della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e141-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="8e141-129">È possibile definire gli operatori di conversione sulla struttura usando l' [istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)ed è possibile dichiarare ogni operatore di conversione come `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="8e141-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="8e141-130">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="8e141-130">**Type Characters.**</span></span> <span data-ttu-id="8e141-131">I tipi di dati della struttura non hanno un carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="8e141-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="8e141-132">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="8e141-132">**Framework Type.**</span></span> <span data-ttu-id="8e141-133">Nessun tipo corrispondente nell'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e141-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="8e141-134">Tutte le strutture ereditano dalla classe <xref:System.ValueType?displayProperty=nameWithType>.NET Framework, ma nessuna struttura specifica corrisponde <xref:System.ValueType?displayProperty=nameWithType>a.</span><span class="sxs-lookup"><span data-stu-id="8e141-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="8e141-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e141-135">Example</span></span>

<span data-ttu-id="8e141-136">Nel paradigma seguente viene illustrato il contorno della dichiarazione di una struttura.</span><span class="sxs-lookup"><span data-stu-id="8e141-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="8e141-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e141-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="8e141-138">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8e141-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8e141-139">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="8e141-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8e141-140">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="8e141-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8e141-141">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="8e141-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="8e141-142">Widening</span><span class="sxs-lookup"><span data-stu-id="8e141-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="8e141-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="8e141-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="8e141-144">Strutture</span><span class="sxs-lookup"><span data-stu-id="8e141-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8e141-145">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8e141-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
