---
title: Costruttori statici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: fabcbb084a74334a7a1bcddb9a04cc6705caeb29
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234929"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="7d17e-102">Costruttori statici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7d17e-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="7d17e-103">Un costruttore statico consente di inizializzare gli eventuali dati [static](../../../csharp/language-reference/keywords/static.md) oppure di eseguire un'operazione specifica che deve essere effettuata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="7d17e-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="7d17e-104">Viene chiamato automaticamente prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="7d17e-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 <span data-ttu-id="7d17e-105">I costruttori statici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d17e-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="7d17e-106">Un costruttore statico non accetta modificatori di accesso e non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="7d17e-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="7d17e-107">Un costruttore statico viene chiamato automaticamente per inizializzare la [classe](../../../csharp/language-reference/keywords/class.md) prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="7d17e-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="7d17e-108">Un costruttore statico non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="7d17e-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="7d17e-109">L'utente non può controllare in alcun modo il momento in cui il costruttore statico viene eseguito nel programma.</span><span class="sxs-lookup"><span data-stu-id="7d17e-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="7d17e-110">In genere, i costruttori statici sono usati per scrivere voci nel file di log, quando alla classe è associato un file di log.</span><span class="sxs-lookup"><span data-stu-id="7d17e-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="7d17e-111">I costruttori statici risultano utili anche durante la creazione di classi wrapper per il codice non gestito, quando il costruttore può chiamare il metodo `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="7d17e-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="7d17e-112">Se un costruttore statico genera un'eccezione, il runtime non lo chiamerà una seconda volta e il tipo rimarrà non inizializzato per la durata del dominio dell'applicazione in cui il programma è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d17e-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d17e-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d17e-113">Example</span></span>  
 <span data-ttu-id="7d17e-114">In questo esempio la classe `Bus` ha un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="7d17e-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="7d17e-115">Quando viene creata la prima istanza di `Bus` (`bus1`), il costruttore statico viene chiamato per inizializzare la classe.</span><span class="sxs-lookup"><span data-stu-id="7d17e-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="7d17e-116">L'output dell'esempio verifica che il costruttore statico venga eseguito una sola volta, anche se vengono create due istanze di `Bus`, e che venga eseguito prima del costruttore di istanze.</span><span class="sxs-lookup"><span data-stu-id="7d17e-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7d17e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d17e-117">See Also</span></span>

- [<span data-ttu-id="7d17e-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7d17e-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7d17e-119">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="7d17e-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="7d17e-120">Costruttori</span><span class="sxs-lookup"><span data-stu-id="7d17e-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="7d17e-121">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="7d17e-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
- [<span data-ttu-id="7d17e-122">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="7d17e-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
