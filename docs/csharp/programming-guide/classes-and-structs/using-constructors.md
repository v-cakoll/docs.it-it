---
title: Uso dei costruttori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 7d027a67e533cb1ed7b2cea38112b4f585bf5fbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714633"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="cf0e0-102">Utilizzo di costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cf0e0-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="cf0e0-103">Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/keywords/struct.md) viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="cf0e0-104">I costruttori hanno lo stesso nome della classe o dello struct e in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="cf0e0-105">Nell'esempio seguente viene definita una classe denominata `Taxi` usando un costruttore semplice.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="cf0e0-106">Viene quindi creata un'istanza per la classe con l'operatore [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="cf0e0-107">Il costruttore `Taxi` viene richiamato dall'operatore `new` immediatamente dopo l'allocazione della memoria per il nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="cf0e0-108">Un costruttore che non accetta parametri è detto *costruttore senza parametri*.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="cf0e0-109">I costruttori senza parametri vengono richiamati ogni volta che si crea un'istanza per un oggetto usando l'operatore `new` e non vengono specificati argomenti per `new`.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="cf0e0-110">Per altre informazioni, vedere [Costruttori di istanze](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="cf0e0-111">A meno che la classe non sia [statica](../../language-reference/keywords/static.md), le classi senza costruttori ricevono un costruttore senza parametri pubblico dal compilatore C# perché possano creare istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="cf0e0-112">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="cf0e0-113">È possibile impedire che venga creata un'istanza per una classe rendendo il costruttore privato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="cf0e0-114">Per altre informazioni, vedere [Costruttori privati](./private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="cf0e0-115">I costruttori per i tipi [struct](../../language-reference/keywords/struct.md) sono simili ai costruttori di classi, ma gli `structs` non possono contenere un costruttore senza parametri esplicito poiché ne viene specificato automaticamente uno dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="cf0e0-116">Questo costruttore inizializza ogni campo dello `struct` sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="cf0e0-117">Per altre informazioni, vedere [Tabella dei valori predefiniti](../../language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-117">For more information, see [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="cf0e0-118">Il costruttore senza parametri viene tuttavia chiamato solo se si crea un'istanza dello `struct` con `new`.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-118">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="cf0e0-119">Questo codice, ad esempio, usa il costruttore senza parametri per <xref:System.Int32>, in modo da garantire che venga inizializzato l'Integer:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-119">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="cf0e0-120">Il codice seguente, tuttavia, provoca un errore del compilatore perché non usa `new` e poiché tenta di usare un oggetto che non è stato inizializzato:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="cf0e0-121">In alternativa, gli oggetti basati su `structs`, inclusi tutti i tipi numerici incorporati, possono essere inizializzati o assegnati e quindi usati come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="cf0e0-122">La chiamata al costruttore senza parametri per un tipo di valore non è quindi necessaria.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-122">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="cf0e0-123">Sia le classi che gli `structs` possono definire costruttori che accettano parametri.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="cf0e0-124">I costruttori che accettano parametri devono essere chiamati con un'istruzione `new` o un'istruzione di [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-124">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="cf0e0-125">Le classi e gli `structs` possono anche definire più costruttori. Né le une né gli altri devono necessariamente definire un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-125">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="cf0e0-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="cf0e0-127">Questa classe può essere creata usando una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="cf0e0-128">Un costruttore può usare la parola chiave `base` per chiamare il costruttore di una classe di base.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="cf0e0-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="cf0e0-130">In questo esempio il costruttore per la classe di base viene chiamato prima che venga eseguito il blocco per il costruttore.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="cf0e0-131">La parola chiave `base` può essere usata con o senza parametri.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="cf0e0-132">Tutti i parametri per il costruttore possono essere usati come parametri per `base` o come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="cf0e0-133">Per altre informazioni, vedere [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-133">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="cf0e0-134">In una classe derivata, se un costruttore di classe base non viene chiamato in modo esplicito usando la parola chiave `base`, il costruttore senza parametri, se ne esiste uno, viene chiamato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="cf0e0-135">Ciò significa quindi che le seguenti dichiarazioni del costruttore si equivalgono:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="cf0e0-136">Se una classe di base non offre un costruttore senza parametri, la classe derivata deve effettuare una chiamata esplicita a un costruttore di base usando `base`.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-136">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="cf0e0-137">Un costruttore può richiamare un altro costruttore nello stesso oggetto usando la parola chiave [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-137">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="cf0e0-138">Come `base`, `this` può essere utilizzata con o senza parametri e gli eventuali parametri nel costruttore sono disponibili come parametri per `this` o come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="cf0e0-139">Ad esempio, il secondo costruttore nell'esempio precedente può essere riscritto usando `this`:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="cf0e0-140">L'uso della parola chiave `this` nell'esempio precedente causa la chiamata di questo costruttore:</span><span class="sxs-lookup"><span data-stu-id="cf0e0-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="cf0e0-141">I costruttori possono essere contrassegnati come [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-141">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="cf0e0-142">Questi modificatori di accesso definiscono il modo in cui gli utenti della classe possono costruire la classe.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="cf0e0-143">Per altre informazioni, vedere [Modificatori di accesso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-143">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="cf0e0-144">Un costruttore può essere dichiarato statico usando la parola chiave [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-144">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="cf0e0-145">I costruttori statici vengono chiamati automaticamente subito prima dell'accesso ai campi statici e in genere vengono usati per inizializzare i membri delle classi statiche.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="cf0e0-146">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-146">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="cf0e0-147">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cf0e0-147">C# Language Specification</span></span>  

<span data-ttu-id="cf0e0-148">Per altre informazioni, vedere [Costruttori di istanze](~/_csharplang/spec/classes.md#instance-constructors) e [Costruttori statici](~/_csharplang/spec/classes.md#static-constructors) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="cf0e0-148">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="cf0e0-149">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="cf0e0-149">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf0e0-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf0e0-150">See also</span></span>

- [<span data-ttu-id="cf0e0-151">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cf0e0-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cf0e0-152">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="cf0e0-152">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="cf0e0-153">Costruttori</span><span class="sxs-lookup"><span data-stu-id="cf0e0-153">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="cf0e0-154">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="cf0e0-154">Finalizers</span></span>](./destructors.md)
