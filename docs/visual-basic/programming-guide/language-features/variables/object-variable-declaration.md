---
title: Dichiarazione di variabili oggetto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: f5f77b81380d997e078a9f52ac4aae6f6e975575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656282"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="0a53a-102">Dichiarazione di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a53a-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="0a53a-103">Utilizzare una normale istruzione di dichiarazione per dichiarare una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="0a53a-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="0a53a-104">Per il tipo di dati, specificare `Object` (vale a dire il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)) o una classe più specifica da cui è possibile creare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0a53a-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="0a53a-105">Dichiarazione di una variabile come `Object` corrisponde alla dichiarazione come <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a53a-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0a53a-106">Quando si dichiara una variabile con una classe di oggetto specifico, è possibile accedere a tutti i metodi e proprietà esposte da tale classe e le classi da cui eredita.</span><span class="sxs-lookup"><span data-stu-id="0a53a-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="0a53a-107">Se si dichiara una variabile con <xref:System.Object>, può accedere solo i membri del <xref:System.Object> classe, a meno che non si attiva `Option Strict Off` per consentire l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="0a53a-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="0a53a-108">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0a53a-108">Declaration Syntax</span></span>  
 <span data-ttu-id="0a53a-109">Utilizzare la sintassi seguente per dichiarare una variabile oggetto:</span><span class="sxs-lookup"><span data-stu-id="0a53a-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="0a53a-110">È inoltre possibile specificare [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [privata](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), o [statico](../../../../visual-basic/language-reference/modifiers/static.md) nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0a53a-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="0a53a-111">Le dichiarazioni di esempio seguenti sono valide:</span><span class="sxs-lookup"><span data-stu-id="0a53a-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="0a53a-112">L'associazione tardiva e l'associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="0a53a-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="0a53a-113">In alcuni casi la classe specifica è sconosciuta fino a quando non viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="0a53a-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="0a53a-114">In questo caso, è necessario dichiarare la variabile oggetto con il `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0a53a-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="0a53a-115">Crea un riferimento generale a qualsiasi tipo di oggetto e la classe specifica viene assegnata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0a53a-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="0a53a-116">Si tratta di *ad associazione tardiva*.</span><span class="sxs-lookup"><span data-stu-id="0a53a-116">This is called *late binding*.</span></span> <span data-ttu-id="0a53a-117">L'associazione tardiva richiede più tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0a53a-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="0a53a-118">Limita anche il codice per i metodi e proprietà della classe che è stato assegnato più di recente a esso.</span><span class="sxs-lookup"><span data-stu-id="0a53a-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="0a53a-119">Questo può causare errori di run-time se il codice tenta di accedere ai membri di un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="0a53a-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="0a53a-120">Quando si conosce la classe specifica in fase di compilazione, è necessario dichiarare la variabile di oggetto di tale classe.</span><span class="sxs-lookup"><span data-stu-id="0a53a-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="0a53a-121">Questa operazione è definita *associazione anticipata*.</span><span class="sxs-lookup"><span data-stu-id="0a53a-121">This is called *early binding*.</span></span> <span data-ttu-id="0a53a-122">Associazione anticipata migliora le prestazioni e garantisce l'accesso di codice a tutti i metodi e proprietà della classe specifica.</span><span class="sxs-lookup"><span data-stu-id="0a53a-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="0a53a-123">Nelle dichiarazioni di esempio precedente, se la variabile `objA` Usa solo gli oggetti della classe <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, è necessario specificare `As System.Windows.Forms.Label` nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0a53a-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="0a53a-124">Vantaggi offerti dall'associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="0a53a-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="0a53a-125">Dichiarare una variabile oggetto come una classe specifica offre diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="0a53a-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
-   <span data-ttu-id="0a53a-126">Controllo automatico del tipo</span><span class="sxs-lookup"><span data-stu-id="0a53a-126">Automatic type checking</span></span>  
  
-   <span data-ttu-id="0a53a-127">È garantito l'accesso a tutti i membri della classe specifico</span><span class="sxs-lookup"><span data-stu-id="0a53a-127">Guaranteed access to all members of the specific class</span></span>  
  
-   <span data-ttu-id="0a53a-128">Supporto Microsoft IntelliSense nell'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="0a53a-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
-   <span data-ttu-id="0a53a-129">Migliorare la leggibilità del codice</span><span class="sxs-lookup"><span data-stu-id="0a53a-129">Improved readability of your code</span></span>  
  
-   <span data-ttu-id="0a53a-130">Un minor numero di errori nel codice</span><span class="sxs-lookup"><span data-stu-id="0a53a-130">Fewer errors in your code</span></span>  
  
-   <span data-ttu-id="0a53a-131">Rilevata degli errori in fase di compilazione anziché di runtime</span><span class="sxs-lookup"><span data-stu-id="0a53a-131">Errors caught at compile time rather than run time</span></span>  
  
-   <span data-ttu-id="0a53a-132">Esecuzione di codice più veloce</span><span class="sxs-lookup"><span data-stu-id="0a53a-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="0a53a-133">Accesso ai membri delle variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="0a53a-134">Quando `Option Strict` sia `On`, una variabile oggetto può accedere solo ai metodi e proprietà della classe con cui viene dichiarata.</span><span class="sxs-lookup"><span data-stu-id="0a53a-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="0a53a-135">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0a53a-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="0a53a-136">In questo esempio `p` può usare solo i membri della classe <xref:System.Object> stessa, che non includono la proprietà `Left` .</span><span class="sxs-lookup"><span data-stu-id="0a53a-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="0a53a-137">D'altra parte, `q` è stata dichiarata con il tipo <xref:System.Windows.Forms.Label>, perciò può usare tutti i metodi e le proprietà della classe <xref:System.Windows.Forms.Label> nello spazio dei nomi <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="0a53a-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="0a53a-138">Flessibilità di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="0a53a-139">Quando si lavora con gli oggetti in una gerarchia di ereditarietà, si dispone di una scelta di quale classe usare per dichiarare le variabili oggetto.</span><span class="sxs-lookup"><span data-stu-id="0a53a-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="0a53a-140">Effettuare questa scelta, è necessario bilanciare la flessibilità dell'assegnazione di oggetto e l'accesso ai membri di una classe.</span><span class="sxs-lookup"><span data-stu-id="0a53a-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="0a53a-141">Si consideri ad esempio la gerarchia di ereditarietà che comporta la <xref:System.Windows.Forms.Form?displayProperty=nameWithType> classe:</span><span class="sxs-lookup"><span data-stu-id="0a53a-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="0a53a-142">Si supponga che l'applicazione definisce una classe del modulo chiamata `specialForm`, che eredita dalla classe <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="0a53a-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="0a53a-143">È possibile dichiarare una variabile oggetto che fa riferimento in modo specifico a `specialForm`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0a53a-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="0a53a-144">La dichiarazione nell'esempio precedente limita la variabile `nextForm` agli oggetti della classe `specialForm`, ma rende anche tutti i metodi e proprietà di `specialForm` disponibili per `nextForm`, nonché per tutti i membri di tutte le classi da cui `specialForm` eredita.</span><span class="sxs-lookup"><span data-stu-id="0a53a-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="0a53a-145">È possibile rendere una variabile oggetto più generale mediante la dichiarazione di tipo <xref:System.Windows.Forms.Form>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0a53a-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="0a53a-146">La dichiarazione nell'esempio precedente consente di assegnare qualsiasi form nell'applicazione per `anyForm`.</span><span class="sxs-lookup"><span data-stu-id="0a53a-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="0a53a-147">Tuttavia, anche se `anyForm` possono accedere tutti i membri della classe <xref:System.Windows.Forms.Form>, non può utilizzare uno dei metodi aggiuntivi o le proprietà definite per moduli specifici, ad esempio `specialForm`.</span><span class="sxs-lookup"><span data-stu-id="0a53a-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="0a53a-148">Tutti i membri di una classe di base sono disponibili per le classi derivate, ma i membri aggiuntivi di una classe derivata non sono disponibili per la classe di base.</span><span class="sxs-lookup"><span data-stu-id="0a53a-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a53a-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a53a-149">See Also</span></span>  
 [<span data-ttu-id="0a53a-150">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="0a53a-151">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="0a53a-152">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="0a53a-153">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a53a-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="0a53a-154">Procedura: accedere ai membri di un oggetto</span><span class="sxs-lookup"><span data-stu-id="0a53a-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [<span data-ttu-id="0a53a-155">Operatore New</span><span class="sxs-lookup"><span data-stu-id="0a53a-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="0a53a-156">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="0a53a-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="0a53a-157">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="0a53a-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
