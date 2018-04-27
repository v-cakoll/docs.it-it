---
title: Determinazione del tipo di un oggetto (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6d24be68ea4a9872f8f4fe89c1aabb943fbcb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="cb080-102">Determinazione del tipo di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb080-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="cb080-103">Variabili oggetto generico (vale a dire le variabili dichiarate come `Object`) possono contenere oggetti di qualsiasi classe.</span><span class="sxs-lookup"><span data-stu-id="cb080-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="cb080-104">Quando si utilizzano variabili di tipo `Object`, potrebbe essere necessario eseguire azioni diverse in base alla classe dell'oggetto, ad esempio, alcuni oggetti potrebbero non supportano una particolare proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="cb080-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="cb080-105">Visual Basic fornisce due modalità per determinare quale tipo di oggetto viene archiviato in una variabile oggetto: il `TypeName` funzione e `TypeOf...Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="cb080-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="cb080-106">TypeName e TypeOf... È</span><span class="sxs-lookup"><span data-stu-id="cb080-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="cb080-107">Il `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cb080-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 <span data-ttu-id="cb080-108">Il `TypeOf...Is` operatore è la scelta migliore per il test del tipo di oggetto, perché è molto più veloce rispetto a un confronto di stringa equivalente con `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="cb080-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="cb080-109">Il frammento di codice seguente utilizza `TypeOf...Is` all'interno di un `If...Then...Else` istruzione:</span><span class="sxs-lookup"><span data-stu-id="cb080-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 <span data-ttu-id="cb080-110">Una parola di attenzione è in scadenza.</span><span class="sxs-lookup"><span data-stu-id="cb080-110">A word of caution is due here.</span></span> <span data-ttu-id="cb080-111">Il `TypeOf...Is` operatore restituisce `True` se un oggetto di un tipo specifico oppure è derivato da un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="cb080-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="cb080-112">Quasi tutte le operazioni eseguite con Visual Basic prevede gli oggetti, inclusi alcuni elementi che normalmente non vengono considerati come oggetti, ad esempio stringhe e numeri interi.</span><span class="sxs-lookup"><span data-stu-id="cb080-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="cb080-113">Questi oggetti derivati da ed ereditano i metodi <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cb080-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="cb080-114">Quando viene passato un `Integer` e valutate con `Object`, `TypeOf...Is` operatore restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="cb080-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="cb080-115">L'esempio seguente segnala che il parametro `InParam` sia un `Object` e `Integer`:</span><span class="sxs-lookup"><span data-stu-id="cb080-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 <span data-ttu-id="cb080-116">L'esempio seguente usa sia `TypeOf...Is` e `TypeName` per determinare il tipo di oggetto passato nel `Ctrl` argomento.</span><span class="sxs-lookup"><span data-stu-id="cb080-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="cb080-117">Il `TestObject` chiamate di procedura `ShowType` con tre diversi tipi di controlli.</span><span class="sxs-lookup"><span data-stu-id="cb080-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="cb080-118">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="cb080-118">To run the example</span></span>  
  
1.  <span data-ttu-id="cb080-119">Creare un nuovo progetto applicazione Windows e aggiungere un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Windows.Forms.CheckBox> (controllo) e un <xref:System.Windows.Forms.RadioButton> al form.</span><span class="sxs-lookup"><span data-stu-id="cb080-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="cb080-120">Dal pulsante sul form, chiamare il `TestObject` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cb080-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="cb080-121">Aggiungere il codice seguente al form:</span><span class="sxs-lookup"><span data-stu-id="cb080-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cb080-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb080-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [<span data-ttu-id="cb080-123">Chiamata di una proprietà o di un metodo mediante un nome di stringa</span><span class="sxs-lookup"><span data-stu-id="cb080-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [<span data-ttu-id="cb080-124">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="cb080-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="cb080-125">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="cb080-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="cb080-126">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="cb080-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="cb080-127">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="cb080-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
