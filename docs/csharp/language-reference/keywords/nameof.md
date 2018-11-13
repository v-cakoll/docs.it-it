---
title: nameof (Riferimenti per C#)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 01c87f8d63264aa342b04b8d3fcfc7e6f38db44b
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "50744356"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="57f81-102">nameof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="57f81-102">nameof (C# Reference)</span></span>

<span data-ttu-id="57f81-103">Usata per ottenere il nome di stringa semplice (non qualificata) di una variabile, un tipo o un membro.</span><span class="sxs-lookup"><span data-stu-id="57f81-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="57f81-104">Quando si segnalano errori nel codice, si associano collegamenti MVC (Model-View-Controller), si attivano eventi di modifica delle proprietà, è spesso necessario acquisire il nome di stringa di un metodo.</span><span class="sxs-lookup"><span data-stu-id="57f81-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="57f81-105">Con `nameof` è possibile garantire la validità del codice in caso di ridenominazione delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="57f81-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="57f81-106">In precedenza, per fare riferimento alle definizioni era necessario usare valori letterali di stringa. Questo approccio tuttavia non è efficace quando si rinominano elementi del codice poiché gli strumenti non hanno l'indicazione di verificare questi valori letterali di stringa.</span><span class="sxs-lookup"><span data-stu-id="57f81-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="57f81-107">Il formato dell'espressione `nameof` è il seguente:</span><span class="sxs-lookup"><span data-stu-id="57f81-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="57f81-108">Casi di utilizzo principali</span><span class="sxs-lookup"><span data-stu-id="57f81-108">Key Use Cases</span></span>  
 <span data-ttu-id="57f81-109">Questi esempi illustrano i casi di utilizzo principali relativi a `nameof`.</span><span class="sxs-lookup"><span data-stu-id="57f81-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="57f81-110">Convalida dei parametri:</span><span class="sxs-lookup"><span data-stu-id="57f81-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="57f81-111">Collegamenti ad azioni MVC:</span><span class="sxs-lookup"><span data-stu-id="57f81-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="57f81-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="57f81-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="57f81-113">Proprietà di dipendenza XAML:</span><span class="sxs-lookup"><span data-stu-id="57f81-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="57f81-114">Registrazione:</span><span class="sxs-lookup"><span data-stu-id="57f81-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="57f81-115">Attributi:</span><span class="sxs-lookup"><span data-stu-id="57f81-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="57f81-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="57f81-116">Examples</span></span>  
 <span data-ttu-id="57f81-117">Alcuni esempi per C#:</span><span class="sxs-lookup"><span data-stu-id="57f81-117">Some C# examples:</span></span>  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a><span data-ttu-id="57f81-118">Note</span><span class="sxs-lookup"><span data-stu-id="57f81-118">Remarks</span></span>  
 <span data-ttu-id="57f81-119">L'argomento di `nameof` deve essere un nome semplice, un nome qualificato, un accesso di tipo membro, un accesso di base con un membro specificato oppure questo accesso con un membro specificato.</span><span class="sxs-lookup"><span data-stu-id="57f81-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="57f81-120">L'espressione dell'argomento identifica una definizione di codice, ma non viene mai valutata.</span><span class="sxs-lookup"><span data-stu-id="57f81-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="57f81-121">Dal momento che l'argomento deve essere un'espressione dal punto di vista sintattico, sono presenti molti elementi non consentiti che non è utile elencare.</span><span class="sxs-lookup"><span data-stu-id="57f81-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="57f81-122">Vale la pena di menzionare i seguenti, che sono quelli che producono errori, ovvero tipi predefiniti (ad esempio `int` o `void`), tipi nullable (`Point?`), tipi di matrice (`Customer[,]`), tipi di puntatore (`Buffer*`), alias qualificati (`A::B`) e tipi generici non associati (`Dictionary<,>`), nonché simboli di pre-elaborazione (`DEBUG`) ed etichette (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="57f81-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="57f81-123">Se è necessario ottenere il nome completo, è possibile usare l'espressione `typeof` unitamente a `nameof`.</span><span class="sxs-lookup"><span data-stu-id="57f81-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="57f81-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="57f81-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="57f81-125">Purtroppo `typeof` non è un'espressione costante come `nameof`, quindi non è possibile usare `typeof` in combinazione con `nameof` in tutti i punti in cui è possibile usare `nameof`.</span><span class="sxs-lookup"><span data-stu-id="57f81-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="57f81-126">Ad esempio, quanto segue genera un errore di compilazione CS0182:</span><span class="sxs-lookup"><span data-stu-id="57f81-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="57f81-127">Negli esempi si nota che è possibile usare un nome di tipi e accedere a un nome di metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="57f81-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="57f81-128">Non è necessario disporre di un'istanza del tipo, come richiesto nelle espressioni valutate.</span><span class="sxs-lookup"><span data-stu-id="57f81-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="57f81-129">In alcune situazioni può risultare molto comodo usare il nome del tipo ma, dal momento che viene fatto riferimento solo al nome senza usare i dati dell'istanza, non è necessario optare per un'espressione o una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="57f81-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="57f81-130">È possibile fare riferimento ai membri di una classe in espressioni di attributo nella classe.</span><span class="sxs-lookup"><span data-stu-id="57f81-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="57f81-131">Non esiste alcun modo per ottenere informazioni sulle firme, ad esempio con "`Method1 (str, str)`".</span><span class="sxs-lookup"><span data-stu-id="57f81-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="57f81-132">A tale scopo è possibile usare un'espressione `Expression e = () => A.B.Method1("s1", "s2")` ed estrarre MemberInfo dall'albero delle espressioni risultante.</span><span class="sxs-lookup"><span data-stu-id="57f81-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="57f81-133">Specifiche del linguaggio</span><span class="sxs-lookup"><span data-stu-id="57f81-133">Language Specifications</span></span>  

<span data-ttu-id="57f81-134">Per altre informazioni, vedere [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="57f81-134">For more information, see [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="57f81-135">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="57f81-135">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="57f81-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57f81-136">See Also</span></span>

- [<span data-ttu-id="57f81-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="57f81-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="57f81-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="57f81-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="57f81-139">typeof</span><span class="sxs-lookup"><span data-stu-id="57f81-139">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
