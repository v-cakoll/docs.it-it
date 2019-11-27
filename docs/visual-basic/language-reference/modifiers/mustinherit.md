---
title: MustInherit
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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351503"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="4ae44-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ae44-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="4ae44-103">Specifica che una classe può essere utilizzata solo come classe base e che non è possibile creare un oggetto direttamente da tale classe.</span><span class="sxs-lookup"><span data-stu-id="4ae44-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ae44-104">Note</span><span class="sxs-lookup"><span data-stu-id="4ae44-104">Remarks</span></span>  
 <span data-ttu-id="4ae44-105">Lo scopo di una *classe di base* (nota anche come *classe astratta*) consiste nel definire la funzionalità comune a tutte le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4ae44-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="4ae44-106">Questo consente di salvare le classi derivate dalla necessità di ridefinire gli elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="4ae44-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="4ae44-107">In alcuni casi, questa funzionalità comune non è sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità mancante.</span><span class="sxs-lookup"><span data-stu-id="4ae44-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="4ae44-108">In tal caso, si desidera che il codice consumer crei oggetti solo dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4ae44-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="4ae44-109">Per applicare questa operazione, è possibile usare `MustInherit` nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="4ae44-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="4ae44-110">Un altro uso di una classe `MustInherit` consiste nel limitare una variabile a un set di classi correlate.</span><span class="sxs-lookup"><span data-stu-id="4ae44-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="4ae44-111">È possibile definire una classe di base e derivare tutte le classi correlate.</span><span class="sxs-lookup"><span data-stu-id="4ae44-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="4ae44-112">La classe base non deve fornire funzionalità comuni a tutte le classi derivate, ma può fungere da filtro per l'assegnazione di valori alle variabili.</span><span class="sxs-lookup"><span data-stu-id="4ae44-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="4ae44-113">Se il codice consumer dichiara una variabile come classe di base, Visual Basic consente di assegnare a tale variabile solo un oggetto da una delle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4ae44-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="4ae44-114">Il .NET Framework definisce diverse classi `MustInherit`, tra cui <xref:System.Array>, <xref:System.Enum>e <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="4ae44-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="4ae44-115"><xref:System.ValueType> è un esempio di una classe di base che limita una variabile.</span><span class="sxs-lookup"><span data-stu-id="4ae44-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="4ae44-116">Tutti i tipi di valore derivano da <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="4ae44-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="4ae44-117">Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo tipi valore a tale variabile.</span><span class="sxs-lookup"><span data-stu-id="4ae44-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4ae44-118">Regole</span><span class="sxs-lookup"><span data-stu-id="4ae44-118">Rules</span></span>  
  
- <span data-ttu-id="4ae44-119">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="4ae44-119">**Declaration Context.**</span></span> <span data-ttu-id="4ae44-120">È possibile utilizzare `MustInherit` solo in un'istruzione `Class`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="4ae44-121">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="4ae44-121">**Combined Modifiers.**</span></span> <span data-ttu-id="4ae44-122">Non è possibile specificare `MustInherit` insieme a `NotInheritable` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="4ae44-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae44-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ae44-123">Example</span></span>  
 <span data-ttu-id="4ae44-124">Nell'esempio seguente viene illustrata l'ereditarietà forzata e l'override forzato.</span><span class="sxs-lookup"><span data-stu-id="4ae44-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="4ae44-125">La classe di base `shape` definisce una variabile `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="4ae44-126">Le classi `circle` e `square` derivano da `shape`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="4ae44-127">Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché il calcolo è diverso per ogni tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="4ae44-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="4ae44-128">È possibile dichiarare `shape1` e `shape2` in modo che siano di tipo `shape`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="4ae44-129">Tuttavia, non è possibile creare un oggetto da `shape` perché manca la funzionalità della funzione `area` ed è contrassegnato `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="4ae44-130">Poiché sono dichiarati come `shape`, le variabili `shape1` e `shape2` sono limitate agli oggetti delle classi derivate `circle` e `square`.</span><span class="sxs-lookup"><span data-stu-id="4ae44-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="4ae44-131">Visual Basic non consente di assegnare altri oggetti a queste variabili, che offre un livello elevato di indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="4ae44-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="4ae44-132">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="4ae44-132">Usage</span></span>  
 <span data-ttu-id="4ae44-133">Il modificatore `MustInherit` può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="4ae44-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="4ae44-134">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="4ae44-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ae44-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ae44-135">See also</span></span>

- [<span data-ttu-id="4ae44-136">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="4ae44-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="4ae44-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="4ae44-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="4ae44-138">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="4ae44-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="4ae44-139">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4ae44-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
