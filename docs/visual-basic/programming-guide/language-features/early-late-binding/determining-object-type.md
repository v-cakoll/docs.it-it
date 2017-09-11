---
title: Determinazione del tipo di oggetto (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fec7a275029dde469425b651d5b1220cb21ddbf6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="c0770-102">Determinazione del tipo di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0770-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="c0770-103">Le variabili oggetto generiche (ovvero, le variabili dichiarate come `Object`) possono contenere oggetti di qualsiasi classe.</span><span class="sxs-lookup"><span data-stu-id="c0770-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="c0770-104">Quando si utilizzano variabili di tipo `Object`, potrebbe essere necessario eseguire azioni diverse in base alla classe dell'oggetto, ad esempio, alcuni oggetti potrebbero non supportare una determinata proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="c0770-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c0770-105">fornisce due modi per determinare quale tipo di oggetto viene archiviato in una variabile oggetto: il `TypeName` funzione e `TypeOf...Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="c0770-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="c0770-106">TypeName e TypeOf... È</span><span class="sxs-lookup"><span data-stu-id="c0770-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="c0770-107">Il `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c0770-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="c0770-108">[!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0770-108">[!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span></span>  
  
 <span data-ttu-id="c0770-109">Il `TypeOf...Is` operatore è la scelta migliore per il test di un tipo di oggetto, perché è molto più veloce rispetto a un confronto di stringa equivalente con `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="c0770-109">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="c0770-110">Il frammento di codice seguente utilizza `TypeOf...Is` all'interno di un `If...Then...Else` istruzione:</span><span class="sxs-lookup"><span data-stu-id="c0770-110">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 <span data-ttu-id="c0770-111">[!code-vb[&#93; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0770-111">[!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span></span>  
  
 <span data-ttu-id="c0770-112">Una precisazione è dovuta qui.</span><span class="sxs-lookup"><span data-stu-id="c0770-112">A word of caution is due here.</span></span> <span data-ttu-id="c0770-113">Il `TypeOf...Is` operatore restituisce `True` se un oggetto è di un tipo specifico oppure è derivato da un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="c0770-113">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="c0770-114">Quasi tutte le operazioni eseguite con [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] all'uso di oggetti, inclusi alcuni elementi che normalmente non vengono considerati come oggetti, ad esempio stringhe e numeri interi.</span><span class="sxs-lookup"><span data-stu-id="c0770-114">Almost everything you do with [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="c0770-115">Questi oggetti derivano da ed ereditano i metodi <xref:System.Object>.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="c0770-115">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="c0770-116">Quando viene passato un `Integer` e valutato con `Object`, `TypeOf...Is` operatore restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="c0770-116">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="c0770-117">L'esempio seguente segnala che il parametro `InParam` è sia un `Object` e `Integer`:</span><span class="sxs-lookup"><span data-stu-id="c0770-117">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 <span data-ttu-id="c0770-118">[!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0770-118">[!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span></span>  
  
 <span data-ttu-id="c0770-119">Nell'esempio seguente utilizza sia `TypeOf...Is` e `TypeName` per determinare il tipo di oggetto passato nel `Ctrl` argomento.</span><span class="sxs-lookup"><span data-stu-id="c0770-119">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="c0770-120">Il `TestObject` le chiamate di procedura `ShowType` con tre diversi tipi di controlli.</span><span class="sxs-lookup"><span data-stu-id="c0770-120">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="c0770-121">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="c0770-121">To run the example</span></span>  
  
1.  <span data-ttu-id="c0770-122">Creare un nuovo progetto applicazione Windows e aggiungere un <xref:System.Windows.Forms.Button>controllo, un <xref:System.Windows.Forms.CheckBox>, controllo e un <xref:System.Windows.Forms.RadioButton>al form.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="c0770-122">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="c0770-123">Dal pulsante sul form, chiamare il `TestObject` procedura.</span><span class="sxs-lookup"><span data-stu-id="c0770-123">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="c0770-124">Aggiungere il codice seguente al form:</span><span class="sxs-lookup"><span data-stu-id="c0770-124">Add the following code to your form:</span></span>  
  
     <span data-ttu-id="c0770-125">[!code-vb[&#95; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0770-125">[!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0770-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0770-126">See Also</span></span>  
 <span data-ttu-id="c0770-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A></span><span class="sxs-lookup"><span data-stu-id="c0770-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></span></span>   
<span data-ttu-id="c0770-128"> [Chiamata di una proprietà o metodo mediante un nome di stringa](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span><span class="sxs-lookup"><span data-stu-id="c0770-128"> [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span></span>  
<span data-ttu-id="c0770-129"> [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="c0770-129"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="c0770-130"> [If... Quindi... Else (istruzione)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c0770-130"> [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span></span>  
<span data-ttu-id="c0770-131"> [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="c0770-131"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="c0770-132"> [Tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="c0770-132"> [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span></span>
