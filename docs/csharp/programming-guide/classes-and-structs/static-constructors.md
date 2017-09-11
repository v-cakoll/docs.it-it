---
title: Costruttori statici (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="0c388-102">Costruttori statici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0c388-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="0c388-103">Un costruttore statico consente di inizializzare gli eventuali dati [static](../../../csharp/language-reference/keywords/static.md) oppure di eseguire un'operazione specifica che deve essere effettuata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0c388-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="0c388-104">Viene chiamato automaticamente prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="0c388-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 <span data-ttu-id="0c388-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0c388-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="0c388-106">I costruttori statici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c388-106">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="0c388-107">Un costruttore statico non accetta modificatori di accesso e non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="0c388-107">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="0c388-108">Un costruttore statico viene chiamato automaticamente per inizializzare la [classe](../../../csharp/language-reference/keywords/class.md) prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="0c388-108">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="0c388-109">Un costruttore statico non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="0c388-109">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="0c388-110">L'utente non può controllare in alcun modo il momento in cui il costruttore statico viene eseguito nel programma.</span><span class="sxs-lookup"><span data-stu-id="0c388-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="0c388-111">In genere, i costruttori statici sono usati per scrivere voci nel file di log, quando alla classe è associato un file di log.</span><span class="sxs-lookup"><span data-stu-id="0c388-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="0c388-112">I costruttori statici risultano utili anche durante la creazione di classi wrapper per il codice non gestito, quando il costruttore può chiamare il metodo `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="0c388-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="0c388-113">Se un costruttore statico genera un'eccezione, il runtime non lo chiamerà una seconda volta e il tipo rimarrà non inizializzato per la durata del dominio dell'applicazione in cui il programma è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c388-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c388-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c388-114">Example</span></span>  
 <span data-ttu-id="0c388-115">In questo esempio la classe `Bus` ha un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="0c388-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="0c388-116">Quando viene creata la prima istanza di `Bus` (`bus1`), il costruttore statico viene chiamato per inizializzare la classe.</span><span class="sxs-lookup"><span data-stu-id="0c388-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="0c388-117">L'output dell'esempio verifica che il costruttore statico venga eseguito una sola volta, anche se vengono create due istanze di `Bus`, e che venga eseguito prima del costruttore di istanze.</span><span class="sxs-lookup"><span data-stu-id="0c388-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 <span data-ttu-id="0c388-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0c388-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c388-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c388-119">See Also</span></span>  
 <span data-ttu-id="0c388-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c388-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0c388-121">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c388-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="0c388-122">[Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="0c388-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="0c388-123">[Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="0c388-123">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 [<span data-ttu-id="0c388-124">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="0c388-124">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

