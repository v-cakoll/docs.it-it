---
title: Come dichiarare, creare un'istanza e usare una guida per la C# programmazione di delegati
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712364"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="f6f72-102">Come dichiarare, creare un'istanza e usare un delegato (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="f6f72-102">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="f6f72-103">In C# 1.0 e versioni successive i delegati possono essere dichiarati come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f6f72-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="f6f72-104">In C# 2.0 è disponibile un metodo più semplice per scrivere la dichiarazione precedente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f6f72-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="f6f72-105">In C# 2.0 e versioni successive, è anche possibile usare un metodo anonimo per dichiarare e inizializzare un [delegato](../../language-reference/builtin-types/reference-types.md), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f6f72-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="f6f72-106">In C# 3.0 e versioni successive, è inoltre possibile dichiarare i delegati e crearne un'istanza usando un'espressione lambda, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f6f72-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="f6f72-107">Per altre informazioni, vedere [Espressioni lambda](../statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f6f72-107">For more information, see [Lambda Expressions](../statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="f6f72-108">Nell'esempio che segue viene illustrato come dichiarare un delegato, crearne un'istanza e usarlo.</span><span class="sxs-lookup"><span data-stu-id="f6f72-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="f6f72-109">La classe `BookDB` incapsula il database di una libreria che gestisce un database di volumi.</span><span class="sxs-lookup"><span data-stu-id="f6f72-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="f6f72-110">Espone un metodo, `ProcessPaperbackBooks`, che ricerca tutti i tascabili all'interno del database e chiama un delegato per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="f6f72-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="f6f72-111">Il tipo `delegate` usato viene denominato `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="f6f72-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="f6f72-112">La classe `Test` usa questa classe per stampare i titoli e il prezzo medio dei tascabili.</span><span class="sxs-lookup"><span data-stu-id="f6f72-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="f6f72-113">L'uso dei delegati consente la separazione ottimale delle funzionalità tra il database della libreria e il codice client.</span><span class="sxs-lookup"><span data-stu-id="f6f72-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="f6f72-114">Il codice client non contiene alcuna informazione sulle modalità di archiviazione dei libri o sul meccanismo che consente al codice di individuare i tascabili.</span><span class="sxs-lookup"><span data-stu-id="f6f72-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="f6f72-115">Il codice della libreria non contiene alcuna informazione sull'elaborazione effettuata sui tascabili individuati.</span><span class="sxs-lookup"><span data-stu-id="f6f72-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f72-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6f72-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f6f72-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f6f72-117">Robust Programming</span></span>  
  
- <span data-ttu-id="f6f72-118">Dichiarazione di un delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="f6f72-119">L'istruzione seguente dichiara un nuovo tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="f6f72-120">Ogni tipo delegato descrive il numero e il tipo degli argomenti e il tipo di valore restituito dai metodi in esso incapsulati.</span><span class="sxs-lookup"><span data-stu-id="f6f72-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="f6f72-121">Ogni volta che è necessario un nuovo set di tipi di argomento o un nuovo tipo di valore restituito, è necessario dichiarare un nuovo tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="f6f72-122">Creazione di un'istanza di un delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="f6f72-123">Dopo aver dichiarato un tipo delegato, è necessario creare un oggetto delegato e associarlo a un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="f6f72-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="f6f72-124">Nell'esempio precedente questa operazione viene eseguita passando il metodo `PrintTitle` al metodo `ProcessPaperbackBooks`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f6f72-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="f6f72-125">In questo modo viene creato un nuovo oggetto delegato associato al metodo [statico](../../language-reference/keywords/static.md)`Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="f6f72-125">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="f6f72-126">Analogamente, il metodo non statico `AddBookToTotal` dell'oggetto `totaller` viene passato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f6f72-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="f6f72-127">In entrambi i casi, al metodo `ProcessPaperbackBooks` viene passato un nuovo oggetto delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="f6f72-128">Dopo la creazione di un delegato, il metodo ad esso associato non viene mai modificato, poiché gli oggetti delegati non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="f6f72-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="f6f72-129">Chiamata a un delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="f6f72-130">Una volta creato, un oggetto delegato viene in genere passato a un altro codice che chiamerà il delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="f6f72-131">Per la chiamata di un oggetto delegato viene usato il nome dell'oggetto stesso, seguito dagli argomenti, racchiusi tra parentesi, che devono essere passati al delegato.</span><span class="sxs-lookup"><span data-stu-id="f6f72-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="f6f72-132">Di seguito viene riportato un esempio di chiamata a un delegato:</span><span class="sxs-lookup"><span data-stu-id="f6f72-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="f6f72-133">Un delegato può essere chiamato in modo sincrono, come in questo esempio, oppure in modo asincrono usando i metodi `BeginInvoke` e `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="f6f72-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f72-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f72-134">See also</span></span>

- [<span data-ttu-id="f6f72-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f6f72-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f6f72-136">Eventi</span><span class="sxs-lookup"><span data-stu-id="f6f72-136">Events</span></span>](../events/index.md)
- [<span data-ttu-id="f6f72-137">Delegati</span><span class="sxs-lookup"><span data-stu-id="f6f72-137">Delegates</span></span>](./index.md)
