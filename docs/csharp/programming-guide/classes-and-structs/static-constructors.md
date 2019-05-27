---
title: Costruttori statici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 110d83caad0c588fa899a4129897784e9c74aab8
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881920"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="9d4e4-102">Costruttori statici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9d4e4-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="9d4e4-103">Un costruttore statico consente di inizializzare gli eventuali dati [static](../../../csharp/language-reference/keywords/static.md) oppure di eseguire un'operazione specifica che deve essere effettuata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="9d4e4-104">Viene chiamato automaticamente prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="9d4e4-105">I costruttori statici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d4e4-105">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="9d4e4-106">Un costruttore statico non accetta modificatori di accesso e non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
- <span data-ttu-id="9d4e4-107">Un costruttore statico viene chiamato automaticamente per inizializzare la [classe](../../../csharp/language-reference/keywords/class.md) prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="9d4e4-108">Si noti che il costruttore statico di un tipo viene chiamato quando un metodo statico assegnato a un evento o un delegato viene chiamato, e non quando tale metodo viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-108">Note that a type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span>
  
- <span data-ttu-id="9d4e4-109">Un costruttore statico non può essere chiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-109">A static constructor cannot be called directly.</span></span>  
  
- <span data-ttu-id="9d4e4-110">L'utente non può controllare in alcun modo il momento in cui il costruttore statico viene eseguito nel programma.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
- <span data-ttu-id="9d4e4-111">In genere, i costruttori statici sono usati per scrivere voci nel file di log, quando alla classe è associato un file di log.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
- <span data-ttu-id="9d4e4-112">I costruttori statici risultano utili anche durante la creazione di classi wrapper per il codice non gestito, quando il costruttore può chiamare il metodo `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
- <span data-ttu-id="9d4e4-113">Se un costruttore statico genera un'eccezione, il runtime non lo chiamerà una seconda volta e il tipo rimarrà non inizializzato per la durata del dominio dell'applicazione in cui il programma è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d4e4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d4e4-114">Example</span></span>  
 <span data-ttu-id="9d4e4-115">In questo esempio la classe `Bus` ha un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="9d4e4-116">Quando viene creata la prima istanza di `Bus` (`bus1`), il costruttore statico viene chiamato per inizializzare la classe.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="9d4e4-117">L'output dell'esempio verifica che il costruttore statico venga eseguito una sola volta, anche se vengono create due istanze di `Bus`, e che venga eseguito prima del costruttore di istanze.</span><span class="sxs-lookup"><span data-stu-id="9d4e4-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="9d4e4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d4e4-118">See also</span></span>

- [<span data-ttu-id="9d4e4-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9d4e4-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9d4e4-120">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="9d4e4-120">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="9d4e4-121">Costruttori</span><span class="sxs-lookup"><span data-stu-id="9d4e4-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="9d4e4-122">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="9d4e4-122">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="9d4e4-123">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="9d4e4-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
