---
title: Classi statiche e membri di classi statiche (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
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
ms.openlocfilehash: 63f46f9ae35b3c699744f7bf61cad3b08b796509
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="b8d2c-102">Classi statiche e membri di classi statiche (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b8d2c-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="b8d2c-103">Una classe [statica](../../../csharp/language-reference/keywords/static.md) corrisponde fondamentalmente a una classe non statica, ma c'è una differenza: di una classe statica non è possibile creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="b8d2c-104">In altre parole, non è possibile usare la parola chiave [new](../../../csharp/language-reference/keywords/new.md) per creare una variabile del tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="b8d2c-105">Poiché non esiste una variabile dell'istanza, si accede ai membri di una classe statica tramite il nome stesso della classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="b8d2c-106">Ad esempio, se si dispone di una classe statica denominata `UtilityClass` che dispone di un metodo pubblico denominato `MethodA`, si chiama il metodo come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b8d2c-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="b8d2c-107">Una classe statica può essere usata come un contenitore adatto per insiemi di metodi che funzionano solo sui parametri di input e non devono ottenere o impostare campi di istanza interni.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="b8d2c-108">Ad esempio, nella libreria di classi .NET Framework, la classe statica <xref:System.Math?displayProperty=fullName> contiene diversi metodi che eseguono operazioni matematiche, senza alcun requisito per archiviare o recuperare dati univoci per una particolare istanza della classe <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=fullName> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="b8d2c-109">In altre parole, si applicano i membri della classe specificando il nome della classe e il nome del metodo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="b8d2c-110">Come per tutti i tipi di classi, le informazioni sul tipo di una classe statica vengono caricate da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Common Language Runtime (CLR) durante il caricamento del programma che fa riferimento alle classi.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="b8d2c-111">Il programma non può specificare esattamente quando la classe verrà caricata.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="b8d2c-112">Tuttavia, è garantito che la classe sarà caricata, che i suoi campi saranno inizializzati e che il costruttore statico sarà chiamato prima che il programma faccia riferimento per la prima volta alla classe stessa.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="b8d2c-113">Un costruttore statico viene chiamato solo un volta e una classe statica rimane in memoria per la durata del dominio dell'applicazione in cui risiede il programma.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8d2c-114">Per creare una classe non statica che consente la creazione di un'unica istanza di se stessa, vedere [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567) (Implementare Singleton in C#).</span><span class="sxs-lookup"><span data-stu-id="b8d2c-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span></span>  
  
 <span data-ttu-id="b8d2c-115">Nell'esempio riportato di seguito sono indicate le principali funzionalità delle classi statiche:</span><span class="sxs-lookup"><span data-stu-id="b8d2c-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="b8d2c-116">Contiene solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="b8d2c-117">Non è possibile crearne istanze.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="b8d2c-118">È sealed.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="b8d2c-119">Non può contenere [costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b8d2c-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="b8d2c-120">La creazione di una classe statica è pertanto analoga alla creazione di una classe che contiene solo membri statici e un costruttore privato,</span><span class="sxs-lookup"><span data-stu-id="b8d2c-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="b8d2c-121">che impedisce la creazione di istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="b8d2c-122">Una classe statica presenta un indubbio vantaggio. Consente infatti al compilatore di verificare che non vengano aggiunti accidentalmente membri di istanze</span><span class="sxs-lookup"><span data-stu-id="b8d2c-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="b8d2c-123">e quindi di garantire che non vengano create istanze di questa classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="b8d2c-124">Le classi statiche sono sealed e pertanto non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="b8d2c-125">Possono ereditare solo dalla classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="b8d2c-126">Le classi statiche non possono contenere un costruttore di istanza; possono però contenere un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="b8d2c-127">Le classi non statiche devono definire anche un costruttore statico se la classe contiene membri statici che richiedono un'inizializzazione più complessa.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="b8d2c-128">Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b8d2c-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d2c-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8d2c-129">Example</span></span>  
 <span data-ttu-id="b8d2c-130">Di seguito è riportato un esempio di una classe statica contenente due metodi che consentono di convertire i valori relativi alla temperatura da gradi Celsius a gradi Fahrenheit e viceversa:</span><span class="sxs-lookup"><span data-stu-id="b8d2c-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 <span data-ttu-id="b8d2c-131">[!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8d2c-131">[!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]</span></span>  
  
## <a name="static-members"></a><span data-ttu-id="b8d2c-132">Membri static</span><span class="sxs-lookup"><span data-stu-id="b8d2c-132">Static Members</span></span>  
 <span data-ttu-id="b8d2c-133">Una classe non statica può contenere metodi, campi, proprietà o eventi statici.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-133">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="b8d2c-134">È possibile chiamare il membro statico di una classe anche quando non sono state create istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-134">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="b8d2c-135">Al membro statico si accede sempre tramite il nome della classe, non tramite il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-135">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="b8d2c-136">Di un membro statico esiste una sola copia, indipendentemente dal numero di istanze della classe create.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-136">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="b8d2c-137">Proprietà e metodi statici non possono accedere a campi non statici ed eventi nel tipo che li contiene e non possono accedere a una variabile dell'istanza di qualsiasi oggetto a meno che non venga esplicitamente passata in un parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-137">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="b8d2c-138">È più frequente dichiarare una classe non statica con alcuni membri statici, che dichiarare un'intera classe come statica.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-138">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="b8d2c-139">Due utilizzi comuni di campi statici sono: tenere un conteggio del numero di oggetti di cui è stata creata un'istanza o archiviare un valore che deve essere condiviso fra tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-139">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="b8d2c-140">I metodi statici possono essere sottoposti a overload ma non a override, perché appartengono alla classe e non a qualsiasi istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-140">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="b8d2c-141">Sebbene non sia possibile dichiarare un campo come `static const`, il campo [const](../../../csharp/language-reference/keywords/const.md) è essenzialmente statico nel comportamento.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-141">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="b8d2c-142">Appartiene al tipo, non a istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-142">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="b8d2c-143">Pertanto, non è possibile accedere ai campi const tramite la stessa notazione `ClassName.MemberName` usata per i campi statici.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-143">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="b8d2c-144">Non è richiesta alcuna istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-144">No object instance is required.</span></span>  
  
 <span data-ttu-id="b8d2c-145">C# non supporta variabili locali statiche (variabili dichiarate nell'ambito del metodo).</span><span class="sxs-lookup"><span data-stu-id="b8d2c-145">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="b8d2c-146">I membri delle classi statiche vengono dichiarati tramite la parola chiave `static` prima del tipo restituito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b8d2c-146">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 <span data-ttu-id="b8d2c-147">[!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8d2c-147">[!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="b8d2c-148">I membri statici vengono inizializzati prima dell'accesso iniziale e prima dell'eventuale chiamata al costruttore statico, se presente.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-148">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="b8d2c-149">Per accedere a un membro di una classe statica, usare il nome della classe anziché il nome di una variabile per specificare la posizione del membro, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b8d2c-149">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 <span data-ttu-id="b8d2c-150">[!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8d2c-150">[!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="b8d2c-151">Se la classe contiene campi statici, fornire un costruttore statico che li inizializzi al caricamento della classe.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-151">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="b8d2c-152">Una chiamata a un metodo statico genera un'istruzione call in Microsoft Intermediate Language (MSIL), mentre una chiamata a un metodo di istanza genera un'istruzione `callvirt` che verifica anche la presenza di riferimenti a un oggetto null.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-152">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="b8d2c-153">Tuttavia, nella maggior parte dei casi, la differenza di prestazioni tra i due non è significativa.</span><span class="sxs-lookup"><span data-stu-id="b8d2c-153">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b8d2c-154">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b8d2c-154">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8d2c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8d2c-155">See Also</span></span>  
 <span data-ttu-id="b8d2c-156">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8d2c-156">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b8d2c-157">[Static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="b8d2c-157">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 <span data-ttu-id="b8d2c-158">[Classi](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="b8d2c-158">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="b8d2c-159">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="b8d2c-159">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="b8d2c-160">[Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="b8d2c-160">[Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) </span></span>  
 [<span data-ttu-id="b8d2c-161">Costruttori di istanza</span><span class="sxs-lookup"><span data-stu-id="b8d2c-161">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)

