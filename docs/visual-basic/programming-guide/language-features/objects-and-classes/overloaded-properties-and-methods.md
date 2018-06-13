---
title: Proprietà di overload e i metodi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652194"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="cc96b-102">Proprietà di overload e i metodi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc96b-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="cc96b-103">Eseguire l'overload è la creazione di più di una stored procedure, il costruttore di istanza o proprietà in una classe con lo stesso nome ma con diversi tipi di argomento.</span><span class="sxs-lookup"><span data-stu-id="cc96b-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="cc96b-104">Utilizzo dell'overload</span><span class="sxs-lookup"><span data-stu-id="cc96b-104">Overloading usage</span></span>

 <span data-ttu-id="cc96b-105">L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano sui tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="cc96b-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="cc96b-106">Ad esempio, una classe che è possibile visualizzare diversi tipi di dati è può presentare `Display` procedure simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="cc96b-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 <span data-ttu-id="cc96b-107">Senza l'overload, è necessario creare nomi distinti per ogni procedura, anche se eseguono la stessa operazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc96b-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 <span data-ttu-id="cc96b-108">L'overload, è facile usare metodi o proprietà, perché fornisce una scelta dei tipi di dati che può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cc96b-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="cc96b-109">Ad esempio, il metodo di overload `Display` metodo descritto in precedenza può essere chiamato con una delle righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc96b-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 <span data-ttu-id="cc96b-110">In fase di esecuzione, Visual Basic chiama la stored procedure corretta in base ai tipi di dati dei parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="cc96b-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="cc96b-111">Regole di overload</span><span class="sxs-lookup"><span data-stu-id="cc96b-111">Overloading rules</span></span>

 <span data-ttu-id="cc96b-112">Creare un membro di overload per una classe mediante l'aggiunta di due o più proprietà o metodi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="cc96b-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="cc96b-113">Ad eccezione dei membri derivati, ogni membro di overload deve avere elenchi di parametri diversi e gli elementi seguenti non possono essere utilizzati come caratteristica di differenziazione quando l'overload di una proprietà o routine:</span><span class="sxs-lookup"><span data-stu-id="cc96b-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="cc96b-114">Modificatori, ad esempio `ByVal` o `ByRef`, che si applicano a un membro o i parametri del membro.</span><span class="sxs-lookup"><span data-stu-id="cc96b-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="cc96b-115">Nomi dei parametri</span><span class="sxs-lookup"><span data-stu-id="cc96b-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="cc96b-116">Tipi restituiti di procedure</span><span class="sxs-lookup"><span data-stu-id="cc96b-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="cc96b-117">Il `Overloads` parola chiave è facoltativa quando l'overload, ma eventuali overload membro utilizza il `Overloads` (parola chiave), quindi tutti gli altri membri in overload con lo stesso nome devono inoltre specificare questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="cc96b-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="cc96b-118">Le classi derivate possono eseguire l'overload di membri ereditati con membri che hanno parametri identici e tipi di parametro, un processo noto come *shadowing in base al nome e firma*.</span><span class="sxs-lookup"><span data-stu-id="cc96b-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="cc96b-119">Se il `Overloads` parola chiave viene utilizzata quando shadowing in base al nome e firma, implementazione della classe derivata del membro verrà utilizzato invece di implementazione nella classe base e sarà disponibile per le istanze di tutti gli altri overload per il membro di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="cc96b-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="cc96b-120">Se il `Overloads` parola chiave viene omessa quando l'overload di un membro ereditato con un membro che dispone di parametri identici e tipi di parametro, quindi viene chiamato l'overload *shadowing in base al nome*.</span><span class="sxs-lookup"><span data-stu-id="cc96b-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="cc96b-121">Shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende disponibili per le istanze della classe derivata e i relativi discendenti tutti gli altri overload.</span><span class="sxs-lookup"><span data-stu-id="cc96b-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="cc96b-122">Il `Overloads` e `Shadows` i modificatori non usati con lo stesso metodo o proprietà.</span><span class="sxs-lookup"><span data-stu-id="cc96b-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="cc96b-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc96b-123">Example</span></span>

 <span data-ttu-id="cc96b-124">L'esempio seguente crea metodi di overload che accettano un `String` o `Decimal` rappresentazione di un importo in dollari e restituiscono una stringa contenente l'imposta sulle vendite.</span><span class="sxs-lookup"><span data-stu-id="cc96b-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="cc96b-125">Per usare questo esempio per creare un metodo di overload</span><span class="sxs-lookup"><span data-stu-id="cc96b-125">To use this example to create an overloaded method</span></span>
  
1.  <span data-ttu-id="cc96b-126">Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="cc96b-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="cc96b-127">Aggiungere il codice seguente alla classe `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="cc96b-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  <span data-ttu-id="cc96b-128">Aggiungere la procedura seguente al form.</span><span class="sxs-lookup"><span data-stu-id="cc96b-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  <span data-ttu-id="cc96b-129">Aggiungere un pulsante al form e chiamare il `ShowTax` stored procedure di `Button1_Click` evento del pulsante.</span><span class="sxs-lookup"><span data-stu-id="cc96b-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="cc96b-130">Eseguire il progetto e fare clic sul pulsante sul form per testare il metodo di overload `ShowTax` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cc96b-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="cc96b-131">In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati.</span><span class="sxs-lookup"><span data-stu-id="cc96b-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="cc96b-132">Quando si fa clic sul pulsante, viene chiamato prima con il metodo di overload un `Price` parametro che è una stringa e il messaggio "prezzo è una stringa.</span><span class="sxs-lookup"><span data-stu-id="cc96b-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="cc96b-133">Imposta è $5.12" viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cc96b-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="cc96b-134">`TaxAmount` viene chiamato con un `Decimal` la seconda volta e il messaggio di valore, "prezzo è un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="cc96b-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="cc96b-135">Imposta è $5.12" viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cc96b-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc96b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc96b-136">See also</span></span>

 [<span data-ttu-id="cc96b-137">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="cc96b-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="cc96b-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc96b-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="cc96b-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="cc96b-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="cc96b-140">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="cc96b-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="cc96b-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="cc96b-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="cc96b-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="cc96b-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="cc96b-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="cc96b-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="cc96b-144">Overload</span><span class="sxs-lookup"><span data-stu-id="cc96b-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="cc96b-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="cc96b-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
