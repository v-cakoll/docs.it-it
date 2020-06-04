---
title: Dichiarazione di variabili oggetto
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
ms.openlocfilehash: b6de52cf738a56a42c82978b54cef31574ab0bcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410361"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="e49f0-102">Dichiarazione di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e49f0-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="e49f0-103">Usare un'istruzione di dichiarazione normale per dichiarare una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="e49f0-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="e49f0-104">Per il tipo di dati, è necessario specificare `Object` (ovvero il [tipo di dati Object](../../../language-reference/data-types/object-data-type.md)) o una classe più specifica da cui creare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e49f0-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="e49f0-105">La dichiarazione di una variabile `Object` equivale alla dichiarazione di come <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e49f0-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="e49f0-106">Quando si dichiara una variabile con una classe di oggetti specifica, può accedere a tutti i metodi e le proprietà esposte da tale classe e dalle classi da cui eredita.</span><span class="sxs-lookup"><span data-stu-id="e49f0-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="e49f0-107">Se si dichiara la variabile con <xref:System.Object> , può accedere solo ai membri della <xref:System.Object> classe, a meno che non si giri `Option Strict Off` per consentire l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="e49f0-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="e49f0-108">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="e49f0-108">Declaration Syntax</span></span>  
 <span data-ttu-id="e49f0-109">Per dichiarare una variabile oggetto, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e49f0-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="e49f0-110">Nella dichiarazione è inoltre possibile specificare [public](../../../language-reference/modifiers/public.md), [protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend` , [private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md)o [static](../../../language-reference/modifiers/static.md) .</span><span class="sxs-lookup"><span data-stu-id="e49f0-110">You can also specify [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md), or [Static](../../../language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="e49f0-111">Le seguenti dichiarazioni di esempio sono valide:</span><span class="sxs-lookup"><span data-stu-id="e49f0-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="e49f0-112">Associazione tardiva e associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="e49f0-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="e49f0-113">A volte la classe specifica è sconosciuta fino a quando non viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="e49f0-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="e49f0-114">In questo caso, è necessario dichiarare la variabile oggetto con il `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e49f0-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="e49f0-115">In questo modo viene creato un riferimento generale a qualsiasi tipo di oggetto e la classe specifica viene assegnata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e49f0-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="e49f0-116">Questa operazione viene chiamata *associazione tardiva*.</span><span class="sxs-lookup"><span data-stu-id="e49f0-116">This is called *late binding*.</span></span> <span data-ttu-id="e49f0-117">Per l'associazione tardiva è necessario tempo di esecuzione aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e49f0-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="e49f0-118">Limita inoltre il codice ai metodi e alle proprietà della classe a cui è stata assegnata più di recente.</span><span class="sxs-lookup"><span data-stu-id="e49f0-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="e49f0-119">Questo può causare errori di run-time se il codice tenta di accedere ai membri di una classe diversa.</span><span class="sxs-lookup"><span data-stu-id="e49f0-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="e49f0-120">Quando si conosce la classe specifica in fase di compilazione, è necessario dichiarare la variabile oggetto in modo che sia di tale classe.</span><span class="sxs-lookup"><span data-stu-id="e49f0-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="e49f0-121">Questa operazione è definita *associazione anticipata*.</span><span class="sxs-lookup"><span data-stu-id="e49f0-121">This is called *early binding*.</span></span> <span data-ttu-id="e49f0-122">L'associazione anticipata consente di migliorare le prestazioni e garantisce l'accesso al codice a tutti i metodi e le proprietà della classe specifica.</span><span class="sxs-lookup"><span data-stu-id="e49f0-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="e49f0-123">Nelle dichiarazioni di esempio precedenti, se la variabile `objA` Usa solo oggetti della classe <xref:System.Windows.Forms.Label?displayProperty=nameWithType> , è necessario specificare `As System.Windows.Forms.Label` nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e49f0-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="e49f0-124">Vantaggi offerti dall'associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="e49f0-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="e49f0-125">La dichiarazione di una variabile oggetto come classe specifica offre diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="e49f0-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="e49f0-126">Controllo dei tipi automatici</span><span class="sxs-lookup"><span data-stu-id="e49f0-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="e49f0-127">Accesso garantito a tutti i membri della classe specifica</span><span class="sxs-lookup"><span data-stu-id="e49f0-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="e49f0-128">Supporto di Microsoft IntelliSense nell'editor di codice</span><span class="sxs-lookup"><span data-stu-id="e49f0-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="e49f0-129">Miglioramento della leggibilità del codice</span><span class="sxs-lookup"><span data-stu-id="e49f0-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="e49f0-130">Minor numero di errori nel codice</span><span class="sxs-lookup"><span data-stu-id="e49f0-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="e49f0-131">Errori rilevati in fase di compilazione anziché in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e49f0-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="e49f0-132">Esecuzione di codice più veloce</span><span class="sxs-lookup"><span data-stu-id="e49f0-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="e49f0-133">Accesso ai membri della variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="e49f0-134">Quando `Option Strict` viene attivato `On` , una variabile oggetto può accedere solo ai metodi e alle proprietà della classe con cui viene dichiarata.</span><span class="sxs-lookup"><span data-stu-id="e49f0-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="e49f0-135">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e49f0-135">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="e49f0-136">In questo esempio `p` può usare solo i membri della classe <xref:System.Object> stessa, che non includono la proprietà `Left` .</span><span class="sxs-lookup"><span data-stu-id="e49f0-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="e49f0-137">D'altra parte, `q` è stata dichiarata con il tipo <xref:System.Windows.Forms.Label>, perciò può usare tutti i metodi e le proprietà della classe <xref:System.Windows.Forms.Label> nello spazio dei nomi <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="e49f0-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="e49f0-138">Flessibilità delle variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="e49f0-139">Quando si utilizzano gli oggetti in una gerarchia di ereditarietà, è possibile scegliere la classe da utilizzare per dichiarare le variabili dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e49f0-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="e49f0-140">Quando si sceglie questa opzione, è necessario bilanciare la flessibilità dell'assegnazione degli oggetti rispetto all'accesso ai membri di una classe.</span><span class="sxs-lookup"><span data-stu-id="e49f0-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="e49f0-141">Si consideri, ad esempio, la gerarchia di ereditarietà che conduce alla <xref:System.Windows.Forms.Form?displayProperty=nameWithType> classe:</span><span class="sxs-lookup"><span data-stu-id="e49f0-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="e49f0-142">Si supponga che l'applicazione definisca una classe Form denominata `specialForm` che eredita dalla classe <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="e49f0-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="e49f0-143">È possibile dichiarare una variabile oggetto che fa riferimento in modo specifico a `specialForm` , come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e49f0-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="e49f0-144">La dichiarazione nell'esempio precedente limita la variabile `nextForm` agli oggetti della classe `specialForm` , ma rende anche tutti i metodi e le proprietà `specialForm` disponibili in `nextForm` , nonché tutti i membri di tutte le classi da cui `specialForm` eredita.</span><span class="sxs-lookup"><span data-stu-id="e49f0-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="e49f0-145">È possibile rendere più generale una variabile oggetto dichiarando che è di tipo <xref:System.Windows.Forms.Form> , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e49f0-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="e49f0-146">La dichiarazione nell'esempio precedente consente di assegnare qualsiasi modulo nell'applicazione a `anyForm` .</span><span class="sxs-lookup"><span data-stu-id="e49f0-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="e49f0-147">Tuttavia, sebbene `anyForm` possa accedere a tutti i membri della classe <xref:System.Windows.Forms.Form> , non può utilizzare i metodi o le proprietà aggiuntivi definiti per formati specifici, ad esempio `specialForm` .</span><span class="sxs-lookup"><span data-stu-id="e49f0-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="e49f0-148">Tutti i membri di una classe di base sono disponibili per le classi derivate, ma i membri aggiuntivi di una classe derivata non sono disponibili per la classe di base.</span><span class="sxs-lookup"><span data-stu-id="e49f0-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49f0-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e49f0-149">See also</span></span>

- [<span data-ttu-id="e49f0-150">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-150">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="e49f0-151">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-151">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="e49f0-152">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-152">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="e49f0-153">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e49f0-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="e49f0-154">Procedura: accedere ai membri di un oggetto</span><span class="sxs-lookup"><span data-stu-id="e49f0-154">How to: Access Members of an Object</span></span>](how-to-access-members-of-an-object.md)
- [<span data-ttu-id="e49f0-155">Operatore New</span><span class="sxs-lookup"><span data-stu-id="e49f0-155">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="e49f0-156">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="e49f0-156">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="e49f0-157">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="e49f0-157">Local Type Inference</span></span>](local-type-inference.md)
