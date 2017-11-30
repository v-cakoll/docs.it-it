---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d384986e42ee69a0f425c1590599aa2c82bc856
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="0046f-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0046f-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="0046f-103">Specifica una classe può essere utilizzata solo come classe base e non è possibile creare un oggetto direttamente da esso.</span><span class="sxs-lookup"><span data-stu-id="0046f-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0046f-104">Note</span><span class="sxs-lookup"><span data-stu-id="0046f-104">Remarks</span></span>  
 <span data-ttu-id="0046f-105">Lo scopo di un *classe di base* (noto anche come un *classe astratta*) consiste nel definire le funzionalità comuni a tutte le classi derivate da esso.</span><span class="sxs-lookup"><span data-stu-id="0046f-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="0046f-106">In questo modo le classi derivate di dover ridefinire gli elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="0046f-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="0046f-107">In alcuni casi, questa funzionalità comune non è sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità mancante.</span><span class="sxs-lookup"><span data-stu-id="0046f-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="0046f-108">In tal caso, si desidera il codice utilizzato per creare oggetti solo dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="0046f-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="0046f-109">Utilizzare `MustInherit` sulla classe di base per attivare la procedura.</span><span class="sxs-lookup"><span data-stu-id="0046f-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="0046f-110">Un altro uso di un `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate.</span><span class="sxs-lookup"><span data-stu-id="0046f-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="0046f-111">È possibile definire una classe di base e ne derivano tutte le classi correlate.</span><span class="sxs-lookup"><span data-stu-id="0046f-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="0046f-112">La classe di base non è necessario fornire qualsiasi funzionalità comuni a tutte le classi derivate, ma può essere utilizzata come un filtro per assegnare valori alle variabili.</span><span class="sxs-lookup"><span data-stu-id="0046f-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="0046f-113">Se il codice utilizzato dichiara una variabile come classe base, Visual Basic consente di assegnare solo un oggetto da una delle classi derivate a tale variabile.</span><span class="sxs-lookup"><span data-stu-id="0046f-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="0046f-114">.NET Framework definisce vari `MustInherit` classi, tra cui <xref:System.Array>, <xref:System.Enum>, e <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="0046f-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="0046f-115"><xref:System.ValueType>è un esempio di una classe di base che limita una variabile.</span><span class="sxs-lookup"><span data-stu-id="0046f-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="0046f-116">Tutti i tipi di valore derivano da <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="0046f-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="0046f-117">Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo i tipi di valore a tale variabile.</span><span class="sxs-lookup"><span data-stu-id="0046f-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0046f-118">Regole</span><span class="sxs-lookup"><span data-stu-id="0046f-118">Rules</span></span>  
  
-   <span data-ttu-id="0046f-119">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="0046f-119">**Declaration Context.**</span></span> <span data-ttu-id="0046f-120">È possibile utilizzare `MustInherit` solo in un `Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0046f-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="0046f-121">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="0046f-121">**Combined Modifiers.**</span></span> <span data-ttu-id="0046f-122">Non è possibile specificare `MustInherit` assieme `NotInheritable` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0046f-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0046f-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="0046f-123">Example</span></span>  
 <span data-ttu-id="0046f-124">L'esempio seguente illustra l'ereditarietà forzata e si esegue l'override forzato.</span><span class="sxs-lookup"><span data-stu-id="0046f-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="0046f-125">La classe di base `shape` definisce una variabile `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="0046f-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="0046f-126">Le classi `circle` e `square` derivano da `shape`.</span><span class="sxs-lookup"><span data-stu-id="0046f-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="0046f-127">Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché tale calcolo è diverso per ogni tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="0046f-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 <span data-ttu-id="0046f-128">È possibile dichiarare `shape1` e `shape2` sia di tipo `shape`.</span><span class="sxs-lookup"><span data-stu-id="0046f-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="0046f-129">Tuttavia, è possibile creare un oggetto da `shape` perché dispone della funzionalità della funzione `area` ed è contrassegnato `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="0046f-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="0046f-130">Dal momento che vengono dichiarate come `shape`, le variabili `shape1` e `shape2` sono limitate a oggetti delle classi derivate `circle` e `square`.</span><span class="sxs-lookup"><span data-stu-id="0046f-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="0046f-131">Visual Basic non è possibile assegnare qualsiasi altro oggetto a queste variabili, che offre un livello elevato dell'indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="0046f-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="0046f-132">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="0046f-132">Usage</span></span>  
 <span data-ttu-id="0046f-133">Il `MustInherit` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="0046f-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="0046f-134">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="0046f-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0046f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0046f-135">See Also</span></span>  
 [<span data-ttu-id="0046f-136">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="0046f-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="0046f-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="0046f-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="0046f-138">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0046f-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="0046f-139">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="0046f-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
