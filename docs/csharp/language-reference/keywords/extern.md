---
title: Modificatore extern - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: c121d810e64b5fa27f105f814253c0752e028a95
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713531"
---
# <a name="extern-c-reference"></a><span data-ttu-id="b8221-102">extern (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b8221-102">extern (C# Reference)</span></span>

<span data-ttu-id="b8221-103">Il modificatore `extern` consente di dichiarare un metodo implementato esternamente.</span><span class="sxs-lookup"><span data-stu-id="b8221-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="b8221-104">Il modificatore `extern` viene utilizzato in genere con l'attributo `DllImport` quando si effettua una chiamata in codice non gestito tramite i servizi di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b8221-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="b8221-105">In questo caso, anche il metodo deve essere dichiarato come `static`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b8221-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

<span data-ttu-id="b8221-106">La parola chiave `extern` può definire anche un alias di assembly esterno, rendendo possibile il riferimento a versioni diverse dello stesso componente dall'interno di un unico assembly.</span><span class="sxs-lookup"><span data-stu-id="b8221-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="b8221-107">Per altre informazioni, vedere [alias esterno](extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="b8221-107">For more information, see [extern alias](extern-alias.md).</span></span>

<span data-ttu-id="b8221-108">È errato usare i modificatori [abstract](abstract.md) e `extern` contemporaneamente per modificare lo stesso membro.</span><span class="sxs-lookup"><span data-stu-id="b8221-108">It is an error to use the [abstract](abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="b8221-109">L'utilizzo del modificatore `extern` indica che il metodo viene implementato all'esterno del codice C#, mentre l'utilizzo del modificatore `abstract` indica che l'implementazione del metodo non viene fornita nella classe.</span><span class="sxs-lookup"><span data-stu-id="b8221-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>

<span data-ttu-id="b8221-110">La parola chiave extern ha un utilizzo più limitato in c# rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="b8221-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="b8221-111">Per confrontare la parola chiave C# con la parola chiave C++, vedere Utilizzo di extern per specificare il collegamento in Riferimenti al linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="b8221-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>

## <a name="example-1"></a><span data-ttu-id="b8221-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b8221-112">Example 1</span></span>

<span data-ttu-id="b8221-113">In questo esempio il programma riceve una stringa dall'utente e la visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b8221-113">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="b8221-114">Il programma utilizza il metodo `MessageBox` importato dalla libreria User32.dll.</span><span class="sxs-lookup"><span data-stu-id="b8221-114">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a><span data-ttu-id="b8221-115">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b8221-115">Example 2</span></span>

<span data-ttu-id="b8221-116">In questo esempio viene illustrato un programma C# che chiama una libreria C (una DLL nativa).</span><span class="sxs-lookup"><span data-stu-id="b8221-116">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>

1. <span data-ttu-id="b8221-117">Creare il seguente file C e denominarlo `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="b8221-117">Create the following C file and name it `cmdll.c`:</span></span>

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. <span data-ttu-id="b8221-118">Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32 dalla directory di installazione di Visual Studio e compilare il file `cmdll.c` digitando **cl -LD cmdll.c** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b8221-118">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl -LD cmdll.c** at the command prompt.</span></span>

3. <span data-ttu-id="b8221-119">Nella stessa directory creare il seguente file C# e denominarlo `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="b8221-119">In the same directory, create the following C# file and name it `cm.cs`:</span></span>

    ```csharp
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

4. <span data-ttu-id="b8221-120">Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32) dalla directory di installazione di Visual Studio e compilare il file `cm.cs` digitando:</span><span class="sxs-lookup"><span data-stu-id="b8221-120">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>

    > <span data-ttu-id="b8221-121">**csc cm.cs** (al prompt dei comandi x64) o **csc-platform:x86 cm.cs** (al prompt dei comandi x32)</span><span class="sxs-lookup"><span data-stu-id="b8221-121">**csc cm.cs** (for the x64 command prompt) —or— **csc -platform:x86 cm.cs** (for the x32 command prompt)</span></span>

    <span data-ttu-id="b8221-122">Verrà creato il file eseguibile `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="b8221-122">This will create the executable file `cm.exe`.</span></span>

5. <span data-ttu-id="b8221-123">Eseguire `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="b8221-123">Run `cm.exe`.</span></span> <span data-ttu-id="b8221-124">Il metodo `SampleMethod` passa il valore 5 al file DLL, che restituisce il valore moltiplicato per 10.</span><span class="sxs-lookup"><span data-stu-id="b8221-124">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="b8221-125">Il programma produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b8221-125">The program produces the following output:</span></span>

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a><span data-ttu-id="b8221-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b8221-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b8221-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8221-127">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="b8221-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b8221-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b8221-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b8221-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b8221-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b8221-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b8221-131">Modificatori</span><span class="sxs-lookup"><span data-stu-id="b8221-131">Modifiers</span></span>](index.md)
