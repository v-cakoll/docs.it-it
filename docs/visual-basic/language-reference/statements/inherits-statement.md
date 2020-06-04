---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 5d88a01f90bc91a88229d19aa2368f8c71075b2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404499"
---
# <a name="inherits-statement"></a><span data-ttu-id="2a329-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="2a329-102">Inherits Statement</span></span>
<span data-ttu-id="2a329-103">Fa in modo che la classe o l'interfaccia corrente erediti gli attributi, le variabili, le proprietà, le procedure e gli eventi da un'altra classe o set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="2a329-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a329-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a329-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="2a329-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2a329-105">Parts</span></span>  
  
|<span data-ttu-id="2a329-106">Termine</span><span class="sxs-lookup"><span data-stu-id="2a329-106">Term</span></span>|<span data-ttu-id="2a329-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="2a329-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="2a329-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2a329-108">Required.</span></span> <span data-ttu-id="2a329-109">Nome della classe da cui deriva questa classe.</span><span class="sxs-lookup"><span data-stu-id="2a329-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="2a329-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="2a329-110">-or-</span></span><br /><br /> <span data-ttu-id="2a329-111">Nomi delle interfacce da cui deriva questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2a329-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="2a329-112">Utilizzare le virgole per separare più nomi.</span><span class="sxs-lookup"><span data-stu-id="2a329-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a329-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a329-113">Remarks</span></span>  
 <span data-ttu-id="2a329-114">Se utilizzata, l' `Inherits` istruzione deve essere la prima riga non vuota non di commento in una definizione di classe o di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2a329-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="2a329-115">Deve seguire immediatamente l' `Class` istruzione o `Interface` .</span><span class="sxs-lookup"><span data-stu-id="2a329-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="2a329-116">È possibile utilizzare `Inherits` solo in una classe o in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2a329-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="2a329-117">Ciò significa che il contesto di dichiarazione per un'ereditarietà non può essere un file di origine, uno spazio dei nomi, una struttura, un modulo, una procedura o un blocco.</span><span class="sxs-lookup"><span data-stu-id="2a329-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2a329-118">Regole</span><span class="sxs-lookup"><span data-stu-id="2a329-118">Rules</span></span>  
  
- <span data-ttu-id="2a329-119">**Ereditarietà della classe.**</span><span class="sxs-lookup"><span data-stu-id="2a329-119">**Class Inheritance.**</span></span> <span data-ttu-id="2a329-120">Se una classe utilizza l' `Inherits` istruzione, è possibile specificare una sola classe di base.</span><span class="sxs-lookup"><span data-stu-id="2a329-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="2a329-121">Una classe non può ereditare da una classe annidata al suo interno.</span><span class="sxs-lookup"><span data-stu-id="2a329-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="2a329-122">**Ereditarietà dell'interfaccia.**</span><span class="sxs-lookup"><span data-stu-id="2a329-122">**Interface Inheritance.**</span></span> <span data-ttu-id="2a329-123">Se un'interfaccia usa l' `Inherits` istruzione, è possibile specificare una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="2a329-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="2a329-124">È possibile ereditare da due interfacce anche se ognuna definisce un membro con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2a329-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="2a329-125">In tal caso, il codice di implementazione deve usare la qualificazione del nome per specificare il membro che sta implementando.</span><span class="sxs-lookup"><span data-stu-id="2a329-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="2a329-126">Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="2a329-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="2a329-127">Un'interfaccia, ad esempio, `Public` non può ereditare da un' `Friend` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2a329-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="2a329-128">Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.</span><span class="sxs-lookup"><span data-stu-id="2a329-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="2a329-129">Un esempio di ereditarietà della classe nel .NET Framework è la <xref:System.ArgumentException> classe, che eredita dalla <xref:System.SystemException> classe.</span><span class="sxs-lookup"><span data-stu-id="2a329-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="2a329-130">In questo modo vengono fornite <xref:System.ArgumentException> tutte le proprietà e le procedure predefinite richieste dalle eccezioni di sistema, ad esempio la <xref:System.Exception.Message%2A> proprietà e il <xref:System.Exception.ToString%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="2a329-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="2a329-131">Un esempio di ereditarietà dell'interfaccia nel .NET Framework è l' <xref:System.Collections.ICollection> interfaccia, che eredita dall' <xref:System.Collections.IEnumerable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2a329-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="2a329-132">Questo fa <xref:System.Collections.ICollection> in modo che erediti la definizione dell'enumeratore necessario per attraversare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="2a329-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a329-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a329-133">Example</span></span>  
 <span data-ttu-id="2a329-134">Nell'esempio seguente viene utilizzata l' `Inherits` istruzione per mostrare in che modo una classe denominata `thisClass` può ereditare tutti i membri di una classe di base denominata `anotherClass` .</span><span class="sxs-lookup"><span data-stu-id="2a329-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="2a329-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a329-135">Example</span></span>  
 <span data-ttu-id="2a329-136">Nell'esempio seguente viene illustrata l'ereditarietà di più interfacce.</span><span class="sxs-lookup"><span data-stu-id="2a329-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="2a329-137">L'interfaccia denominata `thisInterface` include ora tutte le definizioni nelle <xref:System.IComparable> interfacce, <xref:System.IDisposable> e, che <xref:System.IFormattable> i membri ereditati forniscono rispettivamente per il confronto specifico del tipo di due oggetti, il rilascio delle risorse allocate e l'espressione del valore di un oggetto come `String` .</span><span class="sxs-lookup"><span data-stu-id="2a329-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="2a329-138">Una classe che implementa `thisInterface` deve implementare tutti i membri di ogni interfaccia di base.</span><span class="sxs-lookup"><span data-stu-id="2a329-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a329-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a329-139">See also</span></span>

- [<span data-ttu-id="2a329-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="2a329-140">MustInherit</span></span>](../modifiers/mustinherit.md)
- [<span data-ttu-id="2a329-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="2a329-141">NotInheritable</span></span>](../modifiers/notinheritable.md)
- [<span data-ttu-id="2a329-142">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="2a329-142">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="2a329-143">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="2a329-143">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="2a329-144">Interfacce</span><span class="sxs-lookup"><span data-stu-id="2a329-144">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
