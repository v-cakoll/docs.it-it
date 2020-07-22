---
title: Uso dei costruttori - Guida per programmatori C#
description: Questo esempio Mostra come creare un'istanza di una classe usando l'operatore New in C#. Il costruttore semplice viene richiamato dopo l'allocazione della memoria per il nuovo oggetto.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 6b441b04bd6bfcb5564f40a90718e822f56ac21e
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863955"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="7d655-104">Utilizzo di costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7d655-104">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="7d655-105">Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md) viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="7d655-105">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="7d655-106">I costruttori hanno lo stesso nome della classe o dello struct e in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="7d655-106">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="7d655-107">Nell'esempio seguente viene definita una classe denominata `Taxi` usando un costruttore semplice.</span><span class="sxs-lookup"><span data-stu-id="7d655-107">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="7d655-108">Viene quindi creata un'istanza per la classe con l'operatore [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-108">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="7d655-109">Il costruttore `Taxi` viene richiamato dall'operatore `new` immediatamente dopo l'allocazione della memoria per il nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="7d655-109">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="7d655-110">Un costruttore che non accetta parametri è detto *costruttore senza parametri*.</span><span class="sxs-lookup"><span data-stu-id="7d655-110">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="7d655-111">I costruttori senza parametri vengono richiamati ogni volta che si crea un'istanza per un oggetto usando l'operatore `new` e non vengono specificati argomenti per `new`.</span><span class="sxs-lookup"><span data-stu-id="7d655-111">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="7d655-112">Per altre informazioni, vedere [Costruttori di istanze](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-112">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="7d655-113">A meno che la classe non sia [statica](../../language-reference/keywords/static.md), le classi senza costruttori ricevono un costruttore senza parametri pubblico dal compilatore C# perché possano creare istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="7d655-113">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="7d655-114">Per altre informazioni, vedere [classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-114">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="7d655-115">È possibile impedire che venga creata un'istanza per una classe rendendo il costruttore privato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7d655-115">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="7d655-116">Per altre informazioni, vedere [Costruttori privati](./private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-116">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="7d655-117">I costruttori per i tipi [struct](../../language-reference/builtin-types/struct.md) sono simili ai costruttori di classi, ma gli `structs` non possono contenere un costruttore senza parametri esplicito poiché ne viene specificato automaticamente uno dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="7d655-117">Constructors for [struct](../../language-reference/builtin-types/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="7d655-118">Questo costruttore inizializza ogni campo nell'oggetto sul `struct` [valore predefinito](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-118">This constructor initializes each field in the `struct` to the [default value](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="7d655-119">Il costruttore senza parametri viene tuttavia chiamato solo se si crea un'istanza dello `struct` con `new`.</span><span class="sxs-lookup"><span data-stu-id="7d655-119">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="7d655-120">Questo codice, ad esempio, usa il costruttore senza parametri per <xref:System.Int32>, in modo da garantire che venga inizializzato l'Integer:</span><span class="sxs-lookup"><span data-stu-id="7d655-120">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="7d655-121">Il codice seguente, tuttavia, provoca un errore del compilatore perché non usa `new` e poiché tenta di usare un oggetto che non è stato inizializzato:</span><span class="sxs-lookup"><span data-stu-id="7d655-121">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="7d655-122">In alternativa, gli oggetti basati su `structs`, inclusi tutti i tipi numerici incorporati, possono essere inizializzati o assegnati e quindi usati come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7d655-122">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="7d655-123">La chiamata al costruttore senza parametri per un tipo di valore non è quindi necessaria.</span><span class="sxs-lookup"><span data-stu-id="7d655-123">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="7d655-124">Sia le classi che gli `structs` possono definire costruttori che accettano parametri.</span><span class="sxs-lookup"><span data-stu-id="7d655-124">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="7d655-125">I costruttori che accettano parametri devono essere chiamati con un'istruzione `new` o un'istruzione di [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-125">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="7d655-126">Le classi e gli `structs` possono anche definire più costruttori. Né le une né gli altri devono necessariamente definire un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="7d655-126">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="7d655-127">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7d655-127">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="7d655-128">Questa classe può essere creata usando una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d655-128">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="7d655-129">Un costruttore può usare la parola chiave `base` per chiamare il costruttore di una classe di base.</span><span class="sxs-lookup"><span data-stu-id="7d655-129">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="7d655-130">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7d655-130">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="7d655-131">In questo esempio il costruttore per la classe di base viene chiamato prima che venga eseguito il blocco per il costruttore.</span><span class="sxs-lookup"><span data-stu-id="7d655-131">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="7d655-132">La parola chiave `base` può essere usata con o senza parametri.</span><span class="sxs-lookup"><span data-stu-id="7d655-132">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="7d655-133">Tutti i parametri per il costruttore possono essere usati come parametri per `base` o come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7d655-133">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="7d655-134">Per altre informazioni, vedere [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-134">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="7d655-135">In una classe derivata, se un costruttore di classe base non viene chiamato in modo esplicito usando la parola chiave `base`, il costruttore senza parametri, se ne esiste uno, viene chiamato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="7d655-135">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="7d655-136">Ciò significa quindi che le seguenti dichiarazioni del costruttore si equivalgono:</span><span class="sxs-lookup"><span data-stu-id="7d655-136">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="7d655-137">Se una classe di base non offre un costruttore senza parametri, la classe derivata deve effettuare una chiamata esplicita a un costruttore di base usando `base`.</span><span class="sxs-lookup"><span data-stu-id="7d655-137">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="7d655-138">Un costruttore può richiamare un altro costruttore nello stesso oggetto usando la parola chiave [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-138">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="7d655-139">Come `base`, `this` può essere utilizzata con o senza parametri e gli eventuali parametri nel costruttore sono disponibili come parametri per `this` o come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7d655-139">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="7d655-140">Ad esempio, il secondo costruttore nell'esempio precedente può essere riscritto usando `this`:</span><span class="sxs-lookup"><span data-stu-id="7d655-140">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="7d655-141">L'uso della parola chiave `this` nell'esempio precedente causa la chiamata di questo costruttore:</span><span class="sxs-lookup"><span data-stu-id="7d655-141">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="7d655-142">I costruttori possono essere contrassegnati come [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-142">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="7d655-143">Questi modificatori di accesso definiscono il modo in cui gli utenti della classe possono costruire la classe.</span><span class="sxs-lookup"><span data-stu-id="7d655-143">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="7d655-144">Per altre informazioni, vedere [Modificatori di accesso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-144">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="7d655-145">Un costruttore può essere dichiarato statico usando la parola chiave [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-145">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="7d655-146">I costruttori statici vengono chiamati automaticamente subito prima dell'accesso ai campi statici e in genere vengono usati per inizializzare i membri delle classi statiche.</span><span class="sxs-lookup"><span data-stu-id="7d655-146">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="7d655-147">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7d655-147">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7d655-148">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7d655-148">C# Language Specification</span></span>  

<span data-ttu-id="7d655-149">Per altre informazioni, vedere [Costruttori di istanze](~/_csharplang/spec/classes.md#instance-constructors) e [Costruttori statici](~/_csharplang/spec/classes.md#static-constructors) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="7d655-149">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="7d655-150">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="7d655-150">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d655-151">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7d655-151">See also</span></span>

- [<span data-ttu-id="7d655-152">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7d655-152">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d655-153">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="7d655-153">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7d655-154">Costruttori</span><span class="sxs-lookup"><span data-stu-id="7d655-154">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="7d655-155">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="7d655-155">Finalizers</span></span>](./destructors.md)
