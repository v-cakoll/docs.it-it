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
ms.openlocfilehash: 05b1e6b646c519216eba2d4f0df7a3e32f3dafbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661253"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="52575-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52575-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="52575-103">Specifica una classe può essere utilizzata solo come classe di base e non è possibile creare un oggetto direttamente da esso.</span><span class="sxs-lookup"><span data-stu-id="52575-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52575-104">Note</span><span class="sxs-lookup"><span data-stu-id="52575-104">Remarks</span></span>  
 <span data-ttu-id="52575-105">Lo scopo di un *classe di base* (noto anche come un' *classe astratta*) consiste nel definire funzionalità comuni a tutte le classi da esso derivate.</span><span class="sxs-lookup"><span data-stu-id="52575-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="52575-106">In questo modo le classi derivate di dover ridefinire gli elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="52575-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="52575-107">In alcuni casi, queste funzionalità comuni non sono sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità manca.</span><span class="sxs-lookup"><span data-stu-id="52575-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="52575-108">In tal caso, è necessario il codice utilizzato per creare oggetti solo dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="52575-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="52575-109">Si utilizza `MustInherit` nella classe di base per applicare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="52575-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="52575-110">Un altro uso di un `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate.</span><span class="sxs-lookup"><span data-stu-id="52575-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="52575-111">È possibile definire una classe di base e ne derivano tutte le classi correlate.</span><span class="sxs-lookup"><span data-stu-id="52575-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="52575-112">La classe di base non è necessario fornire qualsiasi funzionalità comuni a tutte le classi derivate, ma possono fungere da un filtro per assegnare valori alle variabili.</span><span class="sxs-lookup"><span data-stu-id="52575-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="52575-113">Se il codice consumer dichiara una variabile come la classe di base, Visual Basic consente di assegnare solo un oggetto da una delle classi derivate a tale variabile.</span><span class="sxs-lookup"><span data-stu-id="52575-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="52575-114">.NET Framework definisce vari `MustInherit` classi, tra di essi <xref:System.Array>, <xref:System.Enum>, e <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="52575-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="52575-115"><xref:System.ValueType> è un esempio di una classe di base che limita una variabile.</span><span class="sxs-lookup"><span data-stu-id="52575-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="52575-116">Tutti i tipi valore derivano da <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="52575-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="52575-117">Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo i tipi di valore alla variabile.</span><span class="sxs-lookup"><span data-stu-id="52575-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="52575-118">Regole</span><span class="sxs-lookup"><span data-stu-id="52575-118">Rules</span></span>  
  
- <span data-ttu-id="52575-119">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="52575-119">**Declaration Context.**</span></span> <span data-ttu-id="52575-120">È possibile usare `MustInherit` solo in un `Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="52575-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="52575-121">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="52575-121">**Combined Modifiers.**</span></span> <span data-ttu-id="52575-122">Non è possibile specificare `MustInherit` insieme a `NotInheritable` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="52575-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52575-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="52575-123">Example</span></span>  
 <span data-ttu-id="52575-124">Nell'esempio seguente viene illustrata l'ereditarietà forzata e forzato viene sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="52575-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="52575-125">La classe di base `shape` definisce una variabile `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="52575-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="52575-126">Le classi `circle` e `square` derivano da `shape`.</span><span class="sxs-lookup"><span data-stu-id="52575-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="52575-127">Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché questo calcolo è diverso per ogni tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="52575-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="52575-128">È possibile dichiarare `shape1` e `shape2` di tipo `shape`.</span><span class="sxs-lookup"><span data-stu-id="52575-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="52575-129">Tuttavia, è possibile creare un oggetto dal `shape` perché manca la funzionalità della funzione `area` ed è contrassegnato `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="52575-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="52575-130">Poiché sono stati dichiarati come `shape`, le variabili `shape1` e `shape2` sono limitate a oggetti delle classi derivate `circle` e `square`.</span><span class="sxs-lookup"><span data-stu-id="52575-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="52575-131">Visual Basic non consente di assegnare qualsiasi altro oggetto a queste variabili, che ti offre un elevato livello di indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="52575-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="52575-132">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="52575-132">Usage</span></span>  
 <span data-ttu-id="52575-133">Il `MustInherit` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="52575-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="52575-134">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="52575-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="52575-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52575-135">See also</span></span>

- [<span data-ttu-id="52575-136">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="52575-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="52575-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="52575-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="52575-138">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="52575-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="52575-139">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="52575-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
