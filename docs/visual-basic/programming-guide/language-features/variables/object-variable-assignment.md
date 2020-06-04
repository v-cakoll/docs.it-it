---
title: Assegnazione di variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 9ae1a307e8c886166d516140b7f100a411cedcfa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410374"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="e4862-102">Assegnazione di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4862-102">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="e4862-103">Utilizzare un'istruzione di assegnazione normale per assegnare un oggetto a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4862-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="e4862-104">È possibile assegnare un'espressione di oggetto o la parola chiave [Nothing](../../../language-reference/nothing.md) , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e4862-104">You can assign an object expression or the [Nothing](../../../language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="e4862-105">`Nothing`indica che non è presente alcun oggetto attualmente assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e4862-105">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="e4862-106">Inizializzazione</span><span class="sxs-lookup"><span data-stu-id="e4862-106">Initialization</span></span>

<span data-ttu-id="e4862-107">Quando viene avviata l'esecuzione del codice, le variabili oggetto vengono inizializzate in `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="e4862-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="e4862-108">Quelle le cui dichiarazioni includono l'inizializzazione vengono reinizializzate sui valori specificati durante l'esecuzione delle istruzioni di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e4862-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="e4862-109">È possibile includere l'inizializzazione nella dichiarazione usando la parola chiave [New](../../../language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="e4862-109">You can include initialization in your declaration by using the [New](../../../language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="e4862-110">Le istruzioni di dichiarazione seguenti dichiarano le variabili oggetto `testUri` e `ver` e assegnano oggetti specifici.</span><span class="sxs-lookup"><span data-stu-id="e4862-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="e4862-111">Ogni utilizza uno dei costruttori di overload della classe appropriata per inizializzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4862-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="e4862-112">Dissociazione</span><span class="sxs-lookup"><span data-stu-id="e4862-112">Disassociation</span></span>

<span data-ttu-id="e4862-113">L'impostazione di una variabile oggetto per `Nothing` interrompe l'associazione della variabile a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="e4862-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="e4862-114">Ciò impedisce di modificare accidentalmente l'oggetto modificando la variabile.</span><span class="sxs-lookup"><span data-stu-id="e4862-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="e4862-115">Consente inoltre di verificare se la variabile oggetto punta a un oggetto valido, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e4862-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="e4862-116">Se l'oggetto a cui fa riferimento la variabile si trova in un'altra applicazione, questo test non è in grado di determinare se l'applicazione ha terminato o semplicemente invalidato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4862-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="e4862-117">Una variabile oggetto con un valore di `Nothing` viene anche chiamata *riferimento null*.</span><span class="sxs-lookup"><span data-stu-id="e4862-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="e4862-118">Istanza corrente</span><span class="sxs-lookup"><span data-stu-id="e4862-118">Current Instance</span></span>

<span data-ttu-id="e4862-119">L' *istanza corrente* di un oggetto è quella in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="e4862-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="e4862-120">Poiché tutto il codice viene eseguito all'interno di una routine, l'istanza corrente è quella in cui è stata richiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="e4862-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="e4862-121">La `Me` parola chiave funge da variabile oggetto che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="e4862-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="e4862-122">Se una routine non è [condivisa](../../../language-reference/modifiers/shared.md), può usare la `Me` parola chiave per ottenere un puntatore all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="e4862-122">If a procedure is not [Shared](../../../language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="e4862-123">Le routine condivise non possono essere associate a un'istanza specifica di una classe.</span><span class="sxs-lookup"><span data-stu-id="e4862-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="e4862-124">L'uso di `Me` è particolarmente utile per passare l'istanza corrente a una routine in un altro modulo.</span><span class="sxs-lookup"><span data-stu-id="e4862-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="e4862-125">Si supponga, ad esempio, di avere un numero di documenti XML e di voler aggiungere un testo standard a tutti.</span><span class="sxs-lookup"><span data-stu-id="e4862-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="e4862-126">Nell'esempio seguente viene definita una procedura per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e4862-126">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="e4862-127">Ogni oggetto documento XML potrebbe quindi chiamare la stored procedure e passare l'istanza corrente come argomento.</span><span class="sxs-lookup"><span data-stu-id="e4862-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="e4862-128">L'esempio seguente illustra questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e4862-128">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="e4862-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4862-129">See also</span></span>

- [<span data-ttu-id="e4862-130">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e4862-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="e4862-131">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e4862-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="e4862-132">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e4862-132">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="e4862-133">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4862-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="e4862-134">Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza</span><span class="sxs-lookup"><span data-stu-id="e4862-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="e4862-135">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="e4862-135">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
