---
title: 'Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649165"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="887bb-102">Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="887bb-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="887bb-103">Gli inizializzatori di oggetto consentono di dichiarare e creare un'istanza di una classe in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="887bb-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="887bb-104">Inoltre, è possibile inizializzare uno o più membri dell'istanza nello stesso momento, senza richiamare un costruttore con parametri.</span><span class="sxs-lookup"><span data-stu-id="887bb-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="887bb-105">Quando si utilizza un inizializzatore di oggetto per creare un'istanza di un tipo denominato, viene chiamato il costruttore predefinito per la classe, seguito dall'inizializzazione dei membri designati nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="887bb-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="887bb-106">La procedura seguente viene illustrato come creare un'istanza di un `Student` classe in tre modi diversi.</span><span class="sxs-lookup"><span data-stu-id="887bb-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="887bb-107">La classe dispone di nome, cognome e proprietà della classe anno, tra gli altri.</span><span class="sxs-lookup"><span data-stu-id="887bb-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="887bb-108">Ognuna delle tre dichiarazioni crea una nuova istanza della `Student`, con proprietà `First` impostata su "Michael," proprietà `Last` impostata su "Figli" e impostano tutti gli altri membri in base ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="887bb-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="887bb-109">Il risultato di ogni dichiarazione nella procedura è equivalente all'esempio seguente, che non utilizza un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="887bb-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 <span data-ttu-id="887bb-110">Per un'implementazione del `Student` classe, vedere [procedura: creare un elenco di elementi di](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="887bb-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="887bb-111">È possibile copiare il codice da tale argomento per configurare la classe e creare un elenco di `Student` oggetti da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="887bb-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="887bb-112">Per creare un oggetto di una classe denominata con un inizializzatore di oggetto</span><span class="sxs-lookup"><span data-stu-id="887bb-112">To create an object of a named class by using an object initializer</span></span>  
  
1.  <span data-ttu-id="887bb-113">Iniziare la dichiarazione come se si sceglie di utilizzare un costruttore.</span><span class="sxs-lookup"><span data-stu-id="887bb-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2.  <span data-ttu-id="887bb-114">Digitare la parola chiave `With`, seguito da un elenco di inizializzazione tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="887bb-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  <span data-ttu-id="887bb-115">Nell'elenco di inizializzazione, includere ogni proprietà che si desidera inizializzare e assegnarvi un valore iniziale.</span><span class="sxs-lookup"><span data-stu-id="887bb-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="887bb-116">Il nome della proprietà è preceduto da un punto.</span><span class="sxs-lookup"><span data-stu-id="887bb-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     <span data-ttu-id="887bb-117">È possibile inizializzare uno o più membri della classe.</span><span class="sxs-lookup"><span data-stu-id="887bb-117">You can initialize one or more members of the class.</span></span>  
  
4.  <span data-ttu-id="887bb-118">In alternativa, è possibile dichiarare una nuova istanza della classe e quindi assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="887bb-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="887bb-119">Innanzitutto, dichiarare un'istanza di `Student`:</span><span class="sxs-lookup"><span data-stu-id="887bb-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5.  <span data-ttu-id="887bb-120">Avviare la creazione di un'istanza di `Student` nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="887bb-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6.  <span data-ttu-id="887bb-121">Tipo `With` e quindi un inizializzatore di oggetto per inizializzare i membri di uno o più di una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="887bb-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  <span data-ttu-id="887bb-122">È possibile semplificare la definizione nel passaggio precedente omettendo `As Student`.</span><span class="sxs-lookup"><span data-stu-id="887bb-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="887bb-123">In questo caso, il compilatore determina che `student3` è un'istanza di `Student` tramite l'inferenza del tipo locale.</span><span class="sxs-lookup"><span data-stu-id="887bb-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     <span data-ttu-id="887bb-124">Per ulteriori informazioni, vedere [locale l'inferenza del tipo](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="887bb-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887bb-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="887bb-125">See Also</span></span>  
 [<span data-ttu-id="887bb-126">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="887bb-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="887bb-127">Procedura: Creare un elenco di elementi</span><span class="sxs-lookup"><span data-stu-id="887bb-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [<span data-ttu-id="887bb-128">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="887bb-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="887bb-129">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="887bb-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
