---
title: Metodi e proprietà di overload
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346095"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="3f3ef-102">Metodi e proprietà di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f3ef-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="3f3ef-103">L'overload è la creazione di più di una routine, di un costruttore di istanza o di una proprietà in una classe con lo stesso nome ma con tipi di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="3f3ef-104">Overload dell'utilizzo</span><span class="sxs-lookup"><span data-stu-id="3f3ef-104">Overloading usage</span></span>

<span data-ttu-id="3f3ef-105">L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano su tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="3f3ef-106">Una classe in grado di visualizzare diversi tipi di dati, ad esempio, potrebbe avere `Display` procedure simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="3f3ef-107">Senza l'overload, è necessario creare nomi distinti per ogni routine, anche se eseguono la stessa operazione, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="3f3ef-108">L'overload rende più semplice l'utilizzo di proprietà o metodi perché fornisce una scelta dei tipi di dati che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="3f3ef-109">Ad esempio, il metodo di `Display` di overload illustrato in precedenza può essere chiamato con una delle righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="3f3ef-110">In fase di esecuzione Visual Basic chiama la procedura corretta in base ai tipi di dati dei parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="3f3ef-111">Overload di regole</span><span class="sxs-lookup"><span data-stu-id="3f3ef-111">Overloading rules</span></span>

 <span data-ttu-id="3f3ef-112">Per creare un membro di overload per una classe, è necessario aggiungere due o più proprietà o metodi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="3f3ef-113">Ad eccezione dei membri derivati in overload, ogni membro di overload deve avere elenchi di parametri diversi e gli elementi seguenti non possono essere usati come funzionalità di differenziazione quando si esegue l'overload di una proprietà o di una routine:</span><span class="sxs-lookup"><span data-stu-id="3f3ef-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="3f3ef-114">Modificatori, ad esempio `ByVal` o `ByRef`, che si applicano a un membro o a parametri del membro.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="3f3ef-115">Nomi dei parametri</span><span class="sxs-lookup"><span data-stu-id="3f3ef-115">Names of parameters</span></span>

- <span data-ttu-id="3f3ef-116">Tipi restituiti di routine</span><span class="sxs-lookup"><span data-stu-id="3f3ef-116">Return types of procedures</span></span>

<span data-ttu-id="3f3ef-117">La parola chiave `Overloads` è facoltativa quando si esegue l'overload, ma se un membro di overload usa la parola chiave `Overloads`, tutti gli altri membri di overload con lo stesso nome devono specificare anche questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="3f3ef-118">Le classi derivate possono eseguire l'overload di membri ereditati con membri che hanno parametri e tipi di parametro identici, un processo noto come *ombreggiatura per nome e firma*.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="3f3ef-119">Se la parola chiave `Overloads` viene utilizzata per l'ombreggiatura in base al nome e alla firma, l'implementazione della classe derivata del membro verrà utilizzata al posto dell'implementazione nella classe di base e tutti gli altri overload per quel membro saranno disponibili per le istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="3f3ef-120">Se la parola chiave `Overloads` viene omessa quando si esegue l'overload di un membro ereditato con un membro che ha parametri e tipi di parametro identici, l'overload viene chiamato *ombreggiatura in base al nome*.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="3f3ef-121">Lo shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende non disponibili tutti gli altri overload per le istanze della classe derivata e il relativo discendenti.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="3f3ef-122">I modificatori `Overloads` e `Shadows` non possono essere usati entrambi con la stessa proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="3f3ef-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f3ef-123">Example</span></span>

<span data-ttu-id="3f3ef-124">Nell'esempio seguente vengono creati metodi di overload che accettano una rappresentazione `String` o `Decimal` di un importo in dollari e restituiscono una stringa che contiene l'imposta sulle vendite.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="3f3ef-125">Per usare questo esempio per creare un metodo di overload</span><span class="sxs-lookup"><span data-stu-id="3f3ef-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="3f3ef-126">Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="3f3ef-127">Aggiungere il codice seguente alla classe `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="3f3ef-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="3f3ef-128">Aggiungere la procedura seguente al form.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="3f3ef-129">Aggiungere un pulsante al form e chiamare la procedura `ShowTax` dall'evento `Button1_Click` del pulsante.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="3f3ef-130">Eseguire il progetto e fare clic sul pulsante nel form per testare la procedura di `ShowTax` di overload.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="3f3ef-131">In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="3f3ef-132">Quando si fa clic sul pulsante, il metodo di overload viene chiamato prima con un `Price` parametro che è una stringa e il messaggio "Price è una stringa.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="3f3ef-133">L'imposta è pari a $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="3f3ef-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="3f3ef-134">`TaxAmount` viene chiamato con un valore `Decimal` la seconda volta e il messaggio "Price è un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="3f3ef-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="3f3ef-135">L'imposta è pari a $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="3f3ef-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f3ef-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f3ef-136">See also</span></span>

- [<span data-ttu-id="3f3ef-137">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="3f3ef-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="3f3ef-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f3ef-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="3f3ef-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="3f3ef-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3f3ef-140">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="3f3ef-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="3f3ef-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="3f3ef-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="3f3ef-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="3f3ef-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="3f3ef-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="3f3ef-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="3f3ef-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="3f3ef-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="3f3ef-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="3f3ef-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
