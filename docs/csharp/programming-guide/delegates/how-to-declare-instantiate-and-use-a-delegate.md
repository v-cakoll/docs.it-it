---
title: "Procedura: dichiarare un delegato, crearne un'istanza e utilizzarlo (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 6c53d7572074db44976494e5eed596bf95aaf456
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858860"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="b57e8-102">Procedura: dichiarare un delegato, crearne un'istanza e utilizzarlo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b57e8-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="b57e8-103">In C# 1.0 e versioni successive i delegati possono essere dichiarati come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b57e8-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 <span data-ttu-id="b57e8-104">In C# 2.0 è disponibile un metodo più semplice per scrivere la dichiarazione precedente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b57e8-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 <span data-ttu-id="b57e8-105">In C# 2.0 e versioni successive, è anche possibile usare un metodo anonimo per dichiarare e inizializzare un [delegato](../../../csharp/language-reference/keywords/delegate.md), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b57e8-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 <span data-ttu-id="b57e8-106">In C# 3.0 e versioni successive, è inoltre possibile dichiarare i delegati e crearne un'istanza usando un'espressione lambda, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b57e8-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 <span data-ttu-id="b57e8-107">Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b57e8-107">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="b57e8-108">Nell'esempio che segue viene illustrato come dichiarare un delegato, crearne un'istanza e usarlo.</span><span class="sxs-lookup"><span data-stu-id="b57e8-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="b57e8-109">La classe `BookDB` incapsula il database di una libreria che gestisce un database di volumi.</span><span class="sxs-lookup"><span data-stu-id="b57e8-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="b57e8-110">Espone un metodo, `ProcessPaperbackBooks`, che ricerca tutti i tascabili all'interno del database e chiama un delegato per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="b57e8-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="b57e8-111">Il tipo `delegate` usato viene denominato `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="b57e8-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="b57e8-112">La classe `Test` usa questa classe per stampare i titoli e il prezzo medio dei tascabili.</span><span class="sxs-lookup"><span data-stu-id="b57e8-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="b57e8-113">L'uso dei delegati consente la separazione ottimale delle funzionalità tra il database della libreria e il codice client.</span><span class="sxs-lookup"><span data-stu-id="b57e8-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="b57e8-114">Il codice client non contiene alcuna informazione sulle modalità di archiviazione dei libri o sul meccanismo che consente al codice di individuare i tascabili.</span><span class="sxs-lookup"><span data-stu-id="b57e8-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="b57e8-115">Il codice della libreria non contiene alcuna informazione sull'elaborazione effettuata sui tascabili individuati.</span><span class="sxs-lookup"><span data-stu-id="b57e8-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b57e8-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b57e8-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b57e8-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="b57e8-117">Robust Programming</span></span>  
  
-   <span data-ttu-id="b57e8-118">Dichiarazione di un delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="b57e8-119">L'istruzione seguente dichiara un nuovo tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     <span data-ttu-id="b57e8-120">Ogni tipo delegato descrive il numero e il tipo degli argomenti e il tipo di valore restituito dai metodi in esso incapsulati.</span><span class="sxs-lookup"><span data-stu-id="b57e8-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="b57e8-121">Ogni volta che è necessario un nuovo set di tipi di argomento o un nuovo tipo di valore restituito, è necessario dichiarare un nuovo tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="b57e8-122">Creazione di un'istanza di un delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="b57e8-123">Dopo aver dichiarato un tipo delegato, è necessario creare un oggetto delegato e associarlo a un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="b57e8-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="b57e8-124">Nell'esempio precedente questa operazione viene eseguita passando il metodo `PrintTitle` al metodo `ProcessPaperbackBooks`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b57e8-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     <span data-ttu-id="b57e8-125">In questo modo viene creato un nuovo oggetto delegato associato al metodo [statico](../../../csharp/language-reference/keywords/static.md) `Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="b57e8-125">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="b57e8-126">Analogamente, il metodo non statico `AddBookToTotal` dell'oggetto `totaller` viene passato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b57e8-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     <span data-ttu-id="b57e8-127">In entrambi i casi, al metodo `ProcessPaperbackBooks` viene passato un nuovo oggetto delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="b57e8-128">Dopo la creazione di un delegato, il metodo ad esso associato non viene mai modificato, poiché gli oggetti delegati non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="b57e8-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="b57e8-129">Chiamata a un delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="b57e8-130">Una volta creato, un oggetto delegato viene in genere passato a un altro codice che chiamerà il delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="b57e8-131">Per la chiamata di un oggetto delegato viene usato il nome dell'oggetto stesso, seguito dagli argomenti, racchiusi tra parentesi, che devono essere passati al delegato.</span><span class="sxs-lookup"><span data-stu-id="b57e8-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="b57e8-132">Di seguito viene riportato un esempio di chiamata a un delegato:</span><span class="sxs-lookup"><span data-stu-id="b57e8-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     <span data-ttu-id="b57e8-133">Un delegato può essere chiamato in modo sincrono, come in questo esempio, oppure in modo asincrono usando i metodi `BeginInvoke` e `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="b57e8-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57e8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b57e8-134">See Also</span></span>

- [<span data-ttu-id="b57e8-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b57e8-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b57e8-136">Eventi</span><span class="sxs-lookup"><span data-stu-id="b57e8-136">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="b57e8-137">Delegati</span><span class="sxs-lookup"><span data-stu-id="b57e8-137">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
