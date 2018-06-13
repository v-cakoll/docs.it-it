---
title: Assegnazione di variabili oggetto (Visual Basic)
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
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656058"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="d63d4-102">Assegnazione di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d63d4-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="d63d4-103">Utilizzare una normale istruzione di assegnazione per assegnare un oggetto a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="d63d4-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="d63d4-104">È possibile assegnare un'espressione di oggetto o [nulla](../../../../visual-basic/language-reference/nothing.md) (parola chiave), come nell'esempio riportato di seguito viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="d63d4-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="d63d4-105">`Nothing` indica che nessun oggetto attualmente assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="d63d4-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="d63d4-106">Inizializzazione</span><span class="sxs-lookup"><span data-stu-id="d63d4-106">Initialization</span></span>  
 <span data-ttu-id="d63d4-107">Quando il codice inizia l'esecuzione, l'oggetto le variabili vengono inizializzate su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d63d4-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="d63d4-108">Quelli il cui dichiarazioni includono l'inizializzazione vengono reinizializzati per i valori specificati quando vengono eseguite le istruzioni di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d63d4-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="d63d4-109">È possibile includere nella dichiarazione di inizializzazione utilizzando il [New](../../../../visual-basic/language-reference/operators/new-operator.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d63d4-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="d63d4-110">Le seguenti istruzioni di dichiarazione dichiarano le variabili oggetto `testUri` e `ver` e assegnare loro oggetti specifici.</span><span class="sxs-lookup"><span data-stu-id="d63d4-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="d63d4-111">Ognuno utilizza uno dei costruttori di overload della classe appropriata per inizializzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d63d4-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="d63d4-112">Annullamento dell'associazione</span><span class="sxs-lookup"><span data-stu-id="d63d4-112">Disassociation</span></span>  
 <span data-ttu-id="d63d4-113">Impostare una variabile oggetto `Nothing` interrompe l'associazione della variabile con un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="d63d4-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="d63d4-114">Ciò impedisce di modificare accidentalmente l'oggetto modificando la variabile.</span><span class="sxs-lookup"><span data-stu-id="d63d4-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="d63d4-115">Consente inoltre di verificare se la variabile oggetto punta a un oggetto valido, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d63d4-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="d63d4-116">Se l'oggetto che fa riferimento la variabile in un'altra applicazione, il test non è possibile determinare se l'applicazione ha terminato o semplicemente invalidato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d63d4-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="d63d4-117">Una variabile oggetto con un valore di `Nothing` viene chiamato anche un *riferimento null*.</span><span class="sxs-lookup"><span data-stu-id="d63d4-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="d63d4-118">Istanza corrente</span><span class="sxs-lookup"><span data-stu-id="d63d4-118">Current Instance</span></span>  
 <span data-ttu-id="d63d4-119">Il *istanza corrente* di un oggetto è quello in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="d63d4-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="d63d4-120">Poiché tutto il codice viene eseguito all'interno di una routine, l'istanza corrente è quello in cui è stata richiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="d63d4-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="d63d4-121">Il `Me` (parola chiave) agisce come una variabile oggetto che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="d63d4-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="d63d4-122">Se non è una procedura [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), è possibile usare il `Me` (parola chiave) per ottenere un puntatore all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="d63d4-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="d63d4-123">Procedure condivise non possono essere associate a un'istanza specifica di una classe.</span><span class="sxs-lookup"><span data-stu-id="d63d4-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="d63d4-124">Utilizzando `Me` è particolarmente utile per passare l'istanza corrente a una routine in un altro modulo.</span><span class="sxs-lookup"><span data-stu-id="d63d4-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="d63d4-125">Si supponga, ad esempio, si dispone di un numero di documenti XML e si desidera aggiungere del testo standard di tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d63d4-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="d63d4-126">Nell'esempio seguente definisce una routine a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="d63d4-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="d63d4-127">Ogni oggetto documento XML può quindi chiamare la routine e passa l'istanza corrente come argomento.</span><span class="sxs-lookup"><span data-stu-id="d63d4-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="d63d4-128">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="d63d4-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="d63d4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d63d4-129">See Also</span></span>  
 [<span data-ttu-id="d63d4-130">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="d63d4-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="d63d4-131">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="d63d4-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="d63d4-132">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="d63d4-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="d63d4-133">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d63d4-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="d63d4-134">Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza</span><span class="sxs-lookup"><span data-stu-id="d63d4-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="d63d4-135">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="d63d4-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
