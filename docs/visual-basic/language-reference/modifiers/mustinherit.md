---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816564"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="1cb13-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cb13-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="1cb13-103">Specifica una classe può essere utilizzata solo come classe di base e non è possibile creare un oggetto direttamente da esso.</span><span class="sxs-lookup"><span data-stu-id="1cb13-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cb13-104">Note</span><span class="sxs-lookup"><span data-stu-id="1cb13-104">Remarks</span></span>  
 <span data-ttu-id="1cb13-105">Lo scopo di un *classe di base* (noto anche come un' *classe astratta*) consiste nel definire funzionalità comuni a tutte le classi da esso derivate.</span><span class="sxs-lookup"><span data-stu-id="1cb13-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="1cb13-106">In questo modo le classi derivate di dover ridefinire gli elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="1cb13-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="1cb13-107">In alcuni casi, queste funzionalità comuni non sono sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità manca.</span><span class="sxs-lookup"><span data-stu-id="1cb13-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="1cb13-108">In tal caso, è necessario il codice utilizzato per creare oggetti solo dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="1cb13-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="1cb13-109">Si utilizza `MustInherit` nella classe di base per applicare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="1cb13-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="1cb13-110">Un altro uso di un `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate.</span><span class="sxs-lookup"><span data-stu-id="1cb13-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="1cb13-111">È possibile definire una classe di base e ne derivano tutte le classi correlate.</span><span class="sxs-lookup"><span data-stu-id="1cb13-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="1cb13-112">La classe di base non è necessario fornire qualsiasi funzionalità comuni a tutte le classi derivate, ma possono fungere da un filtro per assegnare valori alle variabili.</span><span class="sxs-lookup"><span data-stu-id="1cb13-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="1cb13-113">Se il codice consumer dichiara una variabile come la classe di base, Visual Basic consente di assegnare solo un oggetto da una delle classi derivate a tale variabile.</span><span class="sxs-lookup"><span data-stu-id="1cb13-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="1cb13-114">.NET Framework definisce vari `MustInherit` classi, tra di essi <xref:System.Array>, <xref:System.Enum>, e <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="1cb13-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="1cb13-115"><xref:System.ValueType> è un esempio di una classe di base che limita una variabile.</span><span class="sxs-lookup"><span data-stu-id="1cb13-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="1cb13-116">Tutti i tipi valore derivano da <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="1cb13-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="1cb13-117">Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo i tipi di valore alla variabile.</span><span class="sxs-lookup"><span data-stu-id="1cb13-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1cb13-118">Regole</span><span class="sxs-lookup"><span data-stu-id="1cb13-118">Rules</span></span>  
  
-   <span data-ttu-id="1cb13-119">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="1cb13-119">**Declaration Context.**</span></span> <span data-ttu-id="1cb13-120">È possibile usare `MustInherit` solo in un `Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1cb13-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="1cb13-121">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="1cb13-121">**Combined Modifiers.**</span></span> <span data-ttu-id="1cb13-122">Non è possibile specificare `MustInherit` insieme a `NotInheritable` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="1cb13-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cb13-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="1cb13-123">Example</span></span>  
 <span data-ttu-id="1cb13-124">Nell'esempio seguente viene illustrata l'ereditarietà forzata e forzato viene sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="1cb13-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="1cb13-125">La classe di base `shape` definisce una variabile `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="1cb13-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="1cb13-126">Le classi `circle` e `square` derivano da `shape`.</span><span class="sxs-lookup"><span data-stu-id="1cb13-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="1cb13-127">Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché questo calcolo è diverso per ogni tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="1cb13-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="1cb13-128">È possibile dichiarare `shape1` e `shape2` di tipo `shape`.</span><span class="sxs-lookup"><span data-stu-id="1cb13-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="1cb13-129">Tuttavia, è possibile creare un oggetto dal `shape` perché manca la funzionalità della funzione `area` ed è contrassegnato `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="1cb13-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="1cb13-130">Poiché sono stati dichiarati come `shape`, le variabili `shape1` e `shape2` sono limitate a oggetti delle classi derivate `circle` e `square`.</span><span class="sxs-lookup"><span data-stu-id="1cb13-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="1cb13-131">Visual Basic non consente di assegnare qualsiasi altro oggetto a queste variabili, che ti offre un elevato livello di indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="1cb13-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="1cb13-132">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="1cb13-132">Usage</span></span>  
 <span data-ttu-id="1cb13-133">Il `MustInherit` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="1cb13-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="1cb13-134">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="1cb13-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1cb13-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cb13-135">See also</span></span>

- [<span data-ttu-id="1cb13-136">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="1cb13-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="1cb13-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="1cb13-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="1cb13-138">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1cb13-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="1cb13-139">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1cb13-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
