---
title: Come intercettare un'eccezione non CLS
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 635cf0a9142f56dea4b2722fbf3f3eda505d85ee
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346282"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="1739c-102">Come intercettare un'eccezione non CLS</span><span class="sxs-lookup"><span data-stu-id="1739c-102">How to catch a non-CLS exception</span></span>
<span data-ttu-id="1739c-103">Alcuni linguaggi .NET, inclusi C++ /CLI, consentono agli oggetti di generare eccezioni che non derivano da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="1739c-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="1739c-104">Tali eccezioni sono chiamate *eccezioni non CLS* o *non eccezioni*.</span><span class="sxs-lookup"><span data-stu-id="1739c-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="1739c-105">In C# non è possibile generare eccezioni non CLS, ma è possibile rilevarle in due modi:</span><span class="sxs-lookup"><span data-stu-id="1739c-105">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="1739c-106">All'interno di un blocco `catch (RuntimeWrappedException e)`.</span><span class="sxs-lookup"><span data-stu-id="1739c-106">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="1739c-107">Per impostazione predefinita, un assembly Visual C# rileva le eccezioni non CLS come eccezioni con wrapper.</span><span class="sxs-lookup"><span data-stu-id="1739c-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="1739c-108">Usare questo metodo se è necessario accedere all'eccezione originale, accessibile tramite la proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1739c-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1739c-109">La procedura illustrata più avanti in questo argomento spiega come rilevare le eccezioni in questo modo.</span><span class="sxs-lookup"><span data-stu-id="1739c-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="1739c-110">All'interno di un blocco catch generale, ovvero un blocco catch senza un tipo di eccezione specificato, posizionato dopo tutti i blocchi `catch`.</span><span class="sxs-lookup"><span data-stu-id="1739c-110">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="1739c-111">Usare questo metodo quando si vuole eseguire un'azione, come ad esempio la scrittura in un file di log, in risposta alle eccezioni non CLS e non è necessario accedere alle informazioni dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1739c-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="1739c-112">Per impostazione predefinita, Common Language Runtime esegue il wrapping di tutte le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1739c-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="1739c-113">Per disabilitare questo comportamento, aggiungere l'attributo a livello di assembly seguente al codice, in genere nel file AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="1739c-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="1739c-114">Per rilevare un'eccezione non CLS</span><span class="sxs-lookup"><span data-stu-id="1739c-114">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="1739c-115">All'interno di un blocco `catch(RuntimeWrappedException e)` accedere all'eccezione originale tramite la proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1739c-115">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1739c-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="1739c-116">Example</span></span>  
 <span data-ttu-id="1739c-117">L'esempio seguente illustra come rilevare un'eccezione non CLS generata da una libreria di classi scritta in C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="1739c-117">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="1739c-118">Si noti che in questo esempio il codice client C# sa in anticipo che il tipo di eccezione generato è <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1739c-118">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1739c-119">È possibile eseguire il cast della proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> al tipo originale, a condizione che tale tipo sia accessibile dal codice.</span><span class="sxs-lookup"><span data-stu-id="1739c-119">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="1739c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1739c-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="1739c-121">Eccezioni e gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="1739c-121">Exceptions and Exception Handling</span></span>](./index.md)
