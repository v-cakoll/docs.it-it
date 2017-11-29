---
title: extern (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 106ceb6a4acf57daa01919acb38e4245655fca2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="extern-c-reference"></a><span data-ttu-id="ca35a-102">extern (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ca35a-102">extern (C# Reference)</span></span>
<span data-ttu-id="ca35a-103">Il modificatore `extern` consente di dichiarare un metodo implementato esternamente.</span><span class="sxs-lookup"><span data-stu-id="ca35a-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="ca35a-104">Il modificatore `extern` viene utilizzato in genere con l'attributo `DllImport` quando si effettua una chiamata in codice non gestito tramite i servizi di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="ca35a-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="ca35a-105">In questo caso, anche il metodo deve essere dichiarato come `static`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ca35a-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="ca35a-106">La parola chiave `extern` può definire anche un alias di assembly esterno, rendendo possibile il riferimento a versioni diverse dello stesso componente dall'interno di un unico assembly.</span><span class="sxs-lookup"><span data-stu-id="ca35a-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="ca35a-107">Per altre informazioni, vedere [alias esterno](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="ca35a-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="ca35a-108">È errato usare i modificatori [abstract](../../../csharp/language-reference/keywords/abstract.md) e `extern` contemporaneamente per modificare lo stesso membro.</span><span class="sxs-lookup"><span data-stu-id="ca35a-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="ca35a-109">L'utilizzo del modificatore `extern` indica che il metodo viene implementato all'esterno del codice C#, mentre l'utilizzo del modificatore `abstract` indica che l'implementazione del metodo non viene fornita nella classe.</span><span class="sxs-lookup"><span data-stu-id="ca35a-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="ca35a-110">La parola chiave extern ha un utilizzo più limitato in c# rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="ca35a-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="ca35a-111">Per confrontare la parola chiave C# con la parola chiave C++, vedere Utilizzo di extern per specificare il collegamento in Riferimenti al linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="ca35a-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca35a-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca35a-112">Example</span></span>  
 <span data-ttu-id="ca35a-113">**Esempio 1.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-113">**Example 1.**</span></span> <span data-ttu-id="ca35a-114">In questo esempio il programma riceve una stringa dall'utente e la visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="ca35a-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="ca35a-115">Il programma utilizza il metodo `MessageBox` importato dalla libreria User32.dll.</span><span class="sxs-lookup"><span data-stu-id="ca35a-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ca35a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca35a-116">Example</span></span>  
 <span data-ttu-id="ca35a-117">**Esempio 2.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-117">**Example 2.**</span></span> <span data-ttu-id="ca35a-118">In questo esempio viene illustrato un programma C# che chiama una libreria C (una DLL nativa).</span><span class="sxs-lookup"><span data-stu-id="ca35a-118">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="ca35a-119">Creare il seguente file C e denominarlo `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="ca35a-119">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="ca35a-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca35a-120">Example</span></span>  
 2. <span data-ttu-id="ca35a-121">Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32 dalla directory di installazione di Visual Studio e compilare il file `cmdll.c` digitando **cl /LD cmdll.c** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ca35a-121">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="ca35a-122">Nella stessa directory creare il seguente file C# e denominarlo `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="ca35a-122">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="ca35a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca35a-123">Example</span></span>  
 3. <span data-ttu-id="ca35a-124">Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32) dalla directory di installazione di Visual Studio e compilare il file `cm.cs` digitando:</span><span class="sxs-lookup"><span data-stu-id="ca35a-124">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="ca35a-125">**csc cm.cs** (al prompt dei comandi x64)</span><span class="sxs-lookup"><span data-stu-id="ca35a-125">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="ca35a-126">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ca35a-126">—or—</span></span>  
> <span data-ttu-id="ca35a-127">**csc /platform:x86 cm.cs** (al prompt dei comandi x32)</span><span class="sxs-lookup"><span data-stu-id="ca35a-127">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="ca35a-128">Verrà creato il file eseguibile `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="ca35a-128">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="ca35a-129">Eseguire `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="ca35a-129">Run `cm.exe`.</span></span> <span data-ttu-id="ca35a-130">Il metodo `SampleMethod` passa il valore 5 al file DLL, che restituisce il valore moltiplicato per 10.</span><span class="sxs-lookup"><span data-stu-id="ca35a-130">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="ca35a-131">Il programma produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ca35a-131">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="ca35a-132">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ca35a-132">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca35a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca35a-133">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>  
 [<span data-ttu-id="ca35a-134">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ca35a-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ca35a-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ca35a-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ca35a-136">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="ca35a-136">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ca35a-137">Modificatori</span><span class="sxs-lookup"><span data-stu-id="ca35a-137">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
