---
title: Tipo di dati definito dall'utente
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a><span data-ttu-id="57c68-102">Tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="57c68-102">User-Defined Data Type</span></span>
<span data-ttu-id="57c68-103">Contiene i dati in un formato definito.</span><span class="sxs-lookup"><span data-stu-id="57c68-103">Holds data in a format you define.</span></span> <span data-ttu-id="57c68-104">Il `Structure` istruzione definisce il formato.</span><span class="sxs-lookup"><span data-stu-id="57c68-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="57c68-105">Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="57c68-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="57c68-106">La versione corrente lo espande in un *struttura*.</span><span class="sxs-lookup"><span data-stu-id="57c68-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="57c68-107">Una struttura è una concatenazione di uno o più *membri* vari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="57c68-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="57c68-108">Viene considerata una struttura di una singola unità, anche se è inoltre possibile accedere singolarmente i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="57c68-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57c68-109">Note</span><span class="sxs-lookup"><span data-stu-id="57c68-109">Remarks</span></span>  
 <span data-ttu-id="57c68-110">Definire e utilizzare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità, o quando nessuno dei tipi di dati elementare servire le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="57c68-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="57c68-111">Il valore predefinito di un tipo di dati di struttura è costituito dalla combinazione dei valori predefiniti di ognuno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="57c68-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="57c68-112">Formato di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="57c68-112">Declaration Format</span></span>  
 <span data-ttu-id="57c68-113">Una dichiarazione di struttura inizia con il [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) e termina con il `End``Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57c68-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End``Structure` statement.</span></span> <span data-ttu-id="57c68-114">Il `Structure` istruzione fornisce il nome della struttura, che è anche l'identificatore del tipo di dati consiste nel definire la struttura.</span><span class="sxs-lookup"><span data-stu-id="57c68-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="57c68-115">Altre parti del codice è possono utilizzare questo identificatore per dichiarare le variabili, parametri e funzione di restituire i valori per questo tipo di struttura dati.</span><span class="sxs-lookup"><span data-stu-id="57c68-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="57c68-116">Le dichiarazioni tra il `Structure` e `End``Structure` istruzioni definiscano i membri della struttura.</span><span class="sxs-lookup"><span data-stu-id="57c68-116">The declarations between the `Structure` and `End``Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="57c68-117">Livelli di accesso di membro</span><span class="sxs-lookup"><span data-stu-id="57c68-117">Member Access Levels</span></span>  
 <span data-ttu-id="57c68-118">È necessario dichiarare ogni membro utilizzando un [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [pubblica](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privato](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="57c68-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="57c68-119">Se si utilizza un `Dim` istruzione, impostazioni predefinite a livello di accesso al ruolo public.</span><span class="sxs-lookup"><span data-stu-id="57c68-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="57c68-120">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="57c68-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="57c68-121">**Utilizzo di memoria.**</span><span class="sxs-lookup"><span data-stu-id="57c68-121">**Memory Consumption.**</span></span> <span data-ttu-id="57c68-122">Come con tutti i tipi di dati compositi, è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura sommando le allocazioni di memoria nominali dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="57c68-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="57c68-123">Inoltre, non è possibile presupporre che l'ordine di archiviazione in memoria è identico all'ordine di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="57c68-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="57c68-124">Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo la `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57c68-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="57c68-125">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="57c68-125">**Interop Considerations.**</span></span> <span data-ttu-id="57c68-126">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic i tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="57c68-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="57c68-127">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="57c68-127">**Widening.**</span></span> <span data-ttu-id="57c68-128">Non è una conversione automatica a o da qualsiasi tipo di dati della struttura.</span><span class="sxs-lookup"><span data-stu-id="57c68-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="57c68-129">È possibile definire gli operatori di conversione per la struttura utilizzando il [Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md), ed è possibile dichiarare ogni operatore di conversione da `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="57c68-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="57c68-130">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="57c68-130">**Type Characters.**</span></span> <span data-ttu-id="57c68-131">Tipi di dati di struttura non dispongono di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="57c68-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="57c68-132">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="57c68-132">**Framework Type.**</span></span> <span data-ttu-id="57c68-133">Non vi è alcun tipo corrispondente in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57c68-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="57c68-134">Tutte le strutture ereditano dalla classe di .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, ma nessuna struttura singola corrisponde a <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57c68-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57c68-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="57c68-135">Example</span></span>  
 <span data-ttu-id="57c68-136">Nell'esempio che segue viene illustrata la struttura della dichiarazione di una struttura.</span><span class="sxs-lookup"><span data-stu-id="57c68-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="57c68-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c68-137">See Also</span></span>  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [<span data-ttu-id="57c68-138">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="57c68-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="57c68-139">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="57c68-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="57c68-140">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="57c68-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="57c68-141">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="57c68-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="57c68-142">Widening</span><span class="sxs-lookup"><span data-stu-id="57c68-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="57c68-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="57c68-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="57c68-144">Strutture</span><span class="sxs-lookup"><span data-stu-id="57c68-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="57c68-145">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="57c68-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
