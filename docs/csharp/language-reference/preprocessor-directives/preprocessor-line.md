---
title: '#line - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 79033fa652af62c76d54737fbf0a0b47cf3aae99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712494"
---
# <a name="line-c-reference"></a><span data-ttu-id="6ebea-102">#line (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6ebea-102">#line (C# Reference)</span></span>

<span data-ttu-id="6ebea-103">`#line` consente di modificare il numero di riga del compilatore e, facoltativamente, l'output del nome del file per gli errori e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6ebea-103">`#line` lets you modify the compiler's line numbering and (optionally) the file name output for errors and warnings.</span></span>

<span data-ttu-id="6ebea-104">Nell'esempio seguente viene illustrata la modalità di segnalazione di due avvisi associati a numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="6ebea-104">The following example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="6ebea-105">La direttiva `#line 200` forza l'impostazione del numero di riga successivo su 200 (anche se l'impostazione predefinita è 6) e, fino alla successiva direttiva `#line`, il nome file viene indicato come "Special".</span><span class="sxs-lookup"><span data-stu-id="6ebea-105">The `#line 200` directive forces the next line's number to be 200 (although the default is #6), and until the next `#line` directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="6ebea-106">La direttiva `#line default` reimposta la numerazione predefinita delle righe, con il conteggio delle righe rinumerate dalla direttiva precedente.</span><span class="sxs-lookup"><span data-stu-id="6ebea-106">The `#line default` directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

<span data-ttu-id="6ebea-107">La compilazione produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="6ebea-107">Compilation produces the following output:</span></span>

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a><span data-ttu-id="6ebea-108">Note</span><span class="sxs-lookup"><span data-stu-id="6ebea-108">Remarks</span></span>

<span data-ttu-id="6ebea-109">La direttiva `#line` può essere usata in un'istruzione automatizzata intermedia nel processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6ebea-109">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="6ebea-110">Se, ad esempio, sono state rimosse delle righe dal file del codice sorgente originale e si vuole che il compilatore generi comunque un output basato sulla numerazione originale delle righe del file, è possibile rimuovere le righe e simulare la numerazione originale tramite `#line`.</span><span class="sxs-lookup"><span data-stu-id="6ebea-110">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>

<span data-ttu-id="6ebea-111">La direttiva `#line hidden` nasconde al debugger le righe successive, in modo che quando lo sviluppatore eseguirà il codice un'istruzione alla volta, verranno eseguite tutte le righe racchiuse tra una direttiva `#line hidden` e la successiva direttiva `#line` (supposto che non si tratti di un'altra direttiva `#line hidden`).</span><span class="sxs-lookup"><span data-stu-id="6ebea-111">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="6ebea-112">Questa opzione può essere usata anche per consentire ad ASP.NET di distinguere il codice definito dall'utente da quello generato dal computer.</span><span class="sxs-lookup"><span data-stu-id="6ebea-112">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="6ebea-113">Sebbene ASP.NET rappresenti il consumer principale di questa funzionalità, è probabile che ne usufruiscano anche altri generatori di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6ebea-113">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>

<span data-ttu-id="6ebea-114">Una direttiva `#line hidden` non influisce sui nomi di file o sui numeri di riga nella segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="6ebea-114">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="6ebea-115">In questo modo, se viene rilevato un errore in un blocco nascosto, nel compilatore verrà segnalato il nome del file corrente e il numero di riga dell'errore.</span><span class="sxs-lookup"><span data-stu-id="6ebea-115">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>

<span data-ttu-id="6ebea-116">La direttiva `#line filename` specifica il nome del file che si vuole venga visualizzato nell'output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6ebea-116">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="6ebea-117">Per impostazione predefinita, viene usato il nome effettivo del file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6ebea-117">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="6ebea-118">Il nome del file deve essere racchiuso tra virgolette doppie (" ") e deve essere preceduto da un numero di riga.</span><span class="sxs-lookup"><span data-stu-id="6ebea-118">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>

<span data-ttu-id="6ebea-119">I file del codice sorgente possono contenere più direttive `#line`.</span><span class="sxs-lookup"><span data-stu-id="6ebea-119">A source code file can have any number of `#line` directives.</span></span>

## <a name="example-1"></a><span data-ttu-id="6ebea-120">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="6ebea-120">Example 1</span></span>

<span data-ttu-id="6ebea-121">Nell'esempio seguente viene illustrato come il debugger ignori le righe nascoste nel codice.</span><span class="sxs-lookup"><span data-stu-id="6ebea-121">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="6ebea-122">Durante l'esecuzione dell'esempio, verranno visualizzate tre righe di testo.</span><span class="sxs-lookup"><span data-stu-id="6ebea-122">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="6ebea-123">Tuttavia, se si imposta un punto di interruzione, come illustrato nell'esempio, e si preme F10 per eseguire il codice un'istruzione alla volta, si noterà che la riga nascosta verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="6ebea-123">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="6ebea-124">La stessa cosa si verifica anche se si imposta un punto di interruzione in corrispondenza della riga nascosta.</span><span class="sxs-lookup"><span data-stu-id="6ebea-124">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6ebea-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ebea-125">See also</span></span>

- [<span data-ttu-id="6ebea-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="6ebea-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ebea-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6ebea-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ebea-128">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="6ebea-128">C# Preprocessor Directives</span></span>](./index.md)
