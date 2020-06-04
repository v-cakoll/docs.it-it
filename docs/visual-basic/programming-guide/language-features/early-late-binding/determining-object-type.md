---
title: Determinazione del tipo di un oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410644"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="b1ed7-102">Determinazione del tipo di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1ed7-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="b1ed7-103">Le variabili oggetto generico, ovvero le variabili dichiarate come, `Object` possono includere oggetti da qualsiasi classe.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="b1ed7-104">Quando si usano variabili di tipo `Object` , potrebbe essere necessario eseguire diverse azioni in base alla classe dell'oggetto. ad esempio, alcuni oggetti potrebbero non supportare una proprietà o un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="b1ed7-105">Visual Basic fornisce due metodi per determinare il tipo di oggetto archiviato in una variabile oggetto, ovvero la `TypeName` funzione e l' `TypeOf...Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="b1ed7-106">TypeName e TypeOf... È</span><span class="sxs-lookup"><span data-stu-id="b1ed7-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="b1ed7-107">La `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b1ed7-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="b1ed7-108">L' `TypeOf...Is` operatore è la scelta migliore per testare il tipo di un oggetto, perché è molto più veloce rispetto a un confronto di stringhe equivalente usando `TypeName` .</span><span class="sxs-lookup"><span data-stu-id="b1ed7-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="b1ed7-109">Nel frammento di codice seguente viene utilizzato `TypeOf...Is` all'interno di un' `If...Then...Else` istruzione:</span><span class="sxs-lookup"><span data-stu-id="b1ed7-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="b1ed7-110">È prevista una parola di attenzione.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-110">A word of caution is due here.</span></span> <span data-ttu-id="b1ed7-111">L' `TypeOf...Is` operatore restituisce `True` se un oggetto è di un tipo specifico o è derivato da un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="b1ed7-112">Quasi tutte le operazioni eseguite con Visual Basic coinvolgono oggetti, che includono alcuni elementi che in genere non sono considerati oggetti, ad esempio stringhe e numeri interi.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="b1ed7-113">Questi oggetti sono derivati da ed ereditano metodi da <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="b1ed7-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="b1ed7-114">Quando viene passato un oggetto `Integer` e valutato con `Object` , l' `TypeOf...Is` operatore restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="b1ed7-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="b1ed7-115">Nell'esempio seguente viene segnalato che il parametro `InParam` è un oggetto `Object` e un oggetto `Integer` :</span><span class="sxs-lookup"><span data-stu-id="b1ed7-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="b1ed7-116">Nell'esempio seguente vengono usati sia `TypeOf...Is` che `TypeName` per determinare il tipo di oggetto passato nell' `Ctrl` argomento.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="b1ed7-117">La `TestObject` procedura chiama `ShowType` con tre tipi diversi di controlli.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="b1ed7-118">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b1ed7-118">To run the example</span></span>  
  
1. <span data-ttu-id="b1ed7-119">Creare un nuovo progetto di applicazione Windows e aggiungere un controllo <xref:System.Windows.Forms.Button> , un controllo <xref:System.Windows.Forms.CheckBox> e un <xref:System.Windows.Forms.RadioButton> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="b1ed7-120">Dal pulsante nel form, chiamare la `TestObject` procedura.</span><span class="sxs-lookup"><span data-stu-id="b1ed7-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="b1ed7-121">Aggiungere il codice seguente al form:</span><span class="sxs-lookup"><span data-stu-id="b1ed7-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="b1ed7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1ed7-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="b1ed7-123">Chiamata di una proprietà o di un metodo mediante un nome di stringa</span><span class="sxs-lookup"><span data-stu-id="b1ed7-123">Calling a Property or Method Using a String Name</span></span>](calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="b1ed7-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b1ed7-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="b1ed7-125">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="b1ed7-125">If...Then...Else Statement</span></span>](../../../language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="b1ed7-126">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="b1ed7-126">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="b1ed7-127">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="b1ed7-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)
