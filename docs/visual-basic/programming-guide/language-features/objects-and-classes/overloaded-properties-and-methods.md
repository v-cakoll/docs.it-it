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
ms.openlocfilehash: 1672f12773ece012c580253b6dafbf9d0ac8f07c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389152"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="5505a-102">Metodi e proprietà di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5505a-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="5505a-103">L'overload è la creazione di più di una routine, di un costruttore di istanza o di una proprietà in una classe con lo stesso nome ma con tipi di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="5505a-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="5505a-104">Overload dell'utilizzo</span><span class="sxs-lookup"><span data-stu-id="5505a-104">Overloading usage</span></span>

<span data-ttu-id="5505a-105">L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano su tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="5505a-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="5505a-106">Una classe in grado di visualizzare diversi tipi di dati, ad esempio, potrebbe avere `Display` procedure simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="5505a-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="5505a-107">Senza l'overload, è necessario creare nomi distinti per ogni routine, anche se eseguono la stessa operazione, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5505a-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="5505a-108">L'overload rende più semplice l'utilizzo di proprietà o metodi perché fornisce una scelta dei tipi di dati che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5505a-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="5505a-109">Il metodo di overload illustrato in precedenza, ad esempio, `Display` può essere chiamato con una delle righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="5505a-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="5505a-110">In fase di esecuzione Visual Basic chiama la procedura corretta in base ai tipi di dati dei parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="5505a-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="5505a-111">Overload di regole</span><span class="sxs-lookup"><span data-stu-id="5505a-111">Overloading rules</span></span>

 <span data-ttu-id="5505a-112">Per creare un membro di overload per una classe, è necessario aggiungere due o più proprietà o metodi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="5505a-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="5505a-113">Ad eccezione dei membri derivati in overload, ogni membro di overload deve avere elenchi di parametri diversi e gli elementi seguenti non possono essere usati come funzionalità di differenziazione quando si esegue l'overload di una proprietà o di una routine:</span><span class="sxs-lookup"><span data-stu-id="5505a-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="5505a-114">Modificatori, ad esempio `ByVal` o `ByRef` , che si applicano a un membro o a parametri del membro.</span><span class="sxs-lookup"><span data-stu-id="5505a-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="5505a-115">Nomi dei parametri</span><span class="sxs-lookup"><span data-stu-id="5505a-115">Names of parameters</span></span>

- <span data-ttu-id="5505a-116">Tipi restituiti di routine</span><span class="sxs-lookup"><span data-stu-id="5505a-116">Return types of procedures</span></span>

<span data-ttu-id="5505a-117">La `Overloads` parola chiave è facoltativa quando si esegue l'overload, ma se un membro di overload usa la `Overloads` parola chiave, anche tutti gli altri membri di overload con lo stesso nome devono specificare questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="5505a-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="5505a-118">Le classi derivate possono eseguire l'overload di membri ereditati con membri che hanno parametri e tipi di parametro identici, un processo noto come *ombreggiatura per nome e firma*.</span><span class="sxs-lookup"><span data-stu-id="5505a-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="5505a-119">Se la `Overloads` parola chiave viene utilizzata per lo shadowing in base al nome e alla firma, l'implementazione della classe derivata del membro verrà utilizzata al posto dell'implementazione nella classe di base, mentre tutti gli altri overload per quel membro saranno disponibili per le istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="5505a-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="5505a-120">Se la `Overloads` parola chiave viene omessa quando si esegue l'overload di un membro ereditato con un membro che ha parametri e tipi di parametro identici, l'overload viene chiamato *ombreggiatura in base al nome*.</span><span class="sxs-lookup"><span data-stu-id="5505a-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="5505a-121">Lo shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende non disponibili tutti gli altri overload per le istanze della classe derivata e il relativo discendenti.</span><span class="sxs-lookup"><span data-stu-id="5505a-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="5505a-122">I `Overloads` `Shadows` modificatori e non possono essere usati entrambi con la stessa proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="5505a-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="5505a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="5505a-123">Example</span></span>

<span data-ttu-id="5505a-124">Nell'esempio seguente vengono creati metodi di overload che accettano una `String` rappresentazione o `Decimal` di un importo in dollari e restituiscono una stringa contenente l'imposta sulle vendite.</span><span class="sxs-lookup"><span data-stu-id="5505a-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="5505a-125">Per usare questo esempio per creare un metodo di overload</span><span class="sxs-lookup"><span data-stu-id="5505a-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="5505a-126">Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="5505a-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="5505a-127">Aggiungere il codice seguente alla classe `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="5505a-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="5505a-128">Aggiungere la procedura seguente al form.</span><span class="sxs-lookup"><span data-stu-id="5505a-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="5505a-129">Aggiungere un pulsante al form e chiamare la `ShowTax` routine dall' `Button1_Click` evento del pulsante.</span><span class="sxs-lookup"><span data-stu-id="5505a-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="5505a-130">Eseguire il progetto e fare clic sul pulsante nel form per testare la procedura di overload `ShowTax` .</span><span class="sxs-lookup"><span data-stu-id="5505a-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="5505a-131">In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati.</span><span class="sxs-lookup"><span data-stu-id="5505a-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="5505a-132">Quando si fa clic sul pulsante, il metodo di overload viene chiamato prima con un `Price` parametro che è una stringa e il messaggio "Price è una stringa.</span><span class="sxs-lookup"><span data-stu-id="5505a-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="5505a-133">L'imposta è pari a $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="5505a-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="5505a-134">`TaxAmount`viene chiamato con un `Decimal` valore la seconda volta e il messaggio "Price è un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="5505a-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="5505a-135">L'imposta è pari a $5,12 ".</span><span class="sxs-lookup"><span data-stu-id="5505a-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="5505a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5505a-136">See also</span></span>

- [<span data-ttu-id="5505a-137">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="5505a-137">Objects and Classes</span></span>](index.md)
- [<span data-ttu-id="5505a-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5505a-138">Shadowing in Visual Basic</span></span>](../declared-elements/shadowing.md)
- [<span data-ttu-id="5505a-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="5505a-139">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5505a-140">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5505a-140">Inheritance Basics</span></span>](inheritance-basics.md)
- [<span data-ttu-id="5505a-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="5505a-141">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="5505a-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="5505a-142">ByVal</span></span>](../../../language-reference/modifiers/byval.md)
- [<span data-ttu-id="5505a-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="5505a-143">ByRef</span></span>](../../../language-reference/modifiers/byref.md)
- [<span data-ttu-id="5505a-144">Overload</span><span class="sxs-lookup"><span data-stu-id="5505a-144">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="5505a-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="5505a-145">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
