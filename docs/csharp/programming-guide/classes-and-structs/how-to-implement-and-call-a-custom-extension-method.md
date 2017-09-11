---
title: 'Procedura: implementare e chiamare un metodo di estensione personalizzato (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
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
ms.openlocfilehash: 8c1c26640c550ce2b16ffafd59430e92189764f9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="b867c-102">Procedura: implementare e chiamare un metodo di estensione personalizzato (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b867c-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="b867c-103">In questo argomento viene illustrato come implementare i propri metodi di estensione per qualsiasi tipo all'interno della [libreria di classi .NET Framework](http://go.microsoft.com/fwlink/?LinkID=217856), o per qualsiasi altro tipo .NET che si voglia estendere.</span><span class="sxs-lookup"><span data-stu-id="b867c-103">This topic shows how to implement your own extension methods for any type in the [.NET Framework Class Library](http://go.microsoft.com/fwlink/?LinkID=217856), or any other .NET type that you want to extend.</span></span> <span data-ttu-id="b867c-104">Il codice client può usare i metodi di estensione aggiungendo un riferimento alla DLL che li contiene, e aggiungendo una direttiva [using](../../../csharp/language-reference/keywords/using-directive.md) che specifica lo spazio dei nomi in cui vengono definiti i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="b867c-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="b867c-105">Per definire e chiamare il metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="b867c-105">To define and call the extension method</span></span>  
  
1.  <span data-ttu-id="b867c-106">Definire una [classe](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) statica per contenere il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="b867c-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="b867c-107">La classe deve essere visibile al codice client.</span><span class="sxs-lookup"><span data-stu-id="b867c-107">The class must be visible to client code.</span></span> <span data-ttu-id="b867c-108">Per altre informazioni sulle regole di accessibilità, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b867c-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2.  <span data-ttu-id="b867c-109">Implementare il metodo di estensione come metodo statico con almeno la stessa visibilità della classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="b867c-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3.  <span data-ttu-id="b867c-110">Il primo parametro del metodo specifica il tipo su cui il metodo opera e deve essere preceduto dal modificatore [this](../../../csharp/language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="b867c-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4.  <span data-ttu-id="b867c-111">Nel codice chiamante, aggiungere una direttiva `using` per specificare lo [spazio dei nomi](../../../csharp/language-reference/keywords/namespace.md) che contiene la classe del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="b867c-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5.  <span data-ttu-id="b867c-112">Chiamare i metodi come se fossero metodi di istanza sul tipo.</span><span class="sxs-lookup"><span data-stu-id="b867c-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="b867c-113">Si noti che il primo parametro non viene specificato tramite la chiamata di codice, poiché rappresenta il tipo su cui viene applicato l'operatore e il compilatore conosce già il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b867c-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="b867c-114">È sufficiente specificare gli argomenti per i parametri da 2 a `n`.</span><span class="sxs-lookup"><span data-stu-id="b867c-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b867c-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b867c-115">Example</span></span>  
 <span data-ttu-id="b867c-116">Nell'esempio seguente un metodo di estensione denominato `WordCount` viene implementato nella classe `CustomExtensions.StringExtension`.</span><span class="sxs-lookup"><span data-stu-id="b867c-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="b867c-117">Il metodo opera sulla classe <xref:System.String>, che viene specificata come primo parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="b867c-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="b867c-118">Lo spazio dei nomi `CustomExtensions` viene importato nello spazio dei nomi dell'applicazione e il metodo viene chiamato all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="b867c-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 <span data-ttu-id="b867c-119">[!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b867c-119">[!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b867c-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b867c-120">Compiling the Code</span></span>  
 <span data-ttu-id="b867c-121">Per eseguire questo codice, copiarlo e incollarlo nel progetto di applicazione console di Visual C# creato in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b867c-121">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="b867c-122">Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e contiene un riferimento a System.Core.dll e una direttiva `using` per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="b867c-122">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="b867c-123">Se uno o più di questi requisiti non sono presenti nel progetto, è possibile aggiungerli manualmente.</span><span class="sxs-lookup"><span data-stu-id="b867c-123">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="net-framework-security"></a><span data-ttu-id="b867c-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b867c-124">.NET Framework Security</span></span>  
 <span data-ttu-id="b867c-125">I metodi di estensione non presentano vulnerabilità di protezione specifiche.</span><span class="sxs-lookup"><span data-stu-id="b867c-125">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="b867c-126">Non possono mai essere usati per rappresentare metodi esistenti su un tipo, perché tutti i conflitti di nomi vengono risolti a favore dell'istanza o del metodo statico definito dal tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="b867c-126">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="b867c-127">I metodi di estensione non possono accedere ai dati privati nella classe estesa.</span><span class="sxs-lookup"><span data-stu-id="b867c-127">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b867c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b867c-128">See Also</span></span>  
 <span data-ttu-id="b867c-129">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b867c-130">[Metodi di estensione](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-130">[Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
 <span data-ttu-id="b867c-131">[LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="b867c-131">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="b867c-132">[Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-132">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 <span data-ttu-id="b867c-133">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-133">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="b867c-134">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-134">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="b867c-135">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-135">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="b867c-136">[this](../../../csharp/language-reference/keywords/this.md) </span><span class="sxs-lookup"><span data-stu-id="b867c-136">[this](../../../csharp/language-reference/keywords/this.md) </span></span>  
 [<span data-ttu-id="b867c-137">namespace</span><span class="sxs-lookup"><span data-stu-id="b867c-137">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)

