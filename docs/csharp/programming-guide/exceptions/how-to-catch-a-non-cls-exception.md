---
title: 'Procedura: intercettare un''eccezione non CLS'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
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
ms.openlocfilehash: 18a19fe34b8ec13bd9fc6d25335d0931a22ce4a3
ms.contentlocale: it-it
ms.lasthandoff: 09/08/2017

---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="a6bc9-102">Procedura: intercettare un'eccezione non CLS</span><span class="sxs-lookup"><span data-stu-id="a6bc9-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="a6bc9-103">Alcuni linguaggi .NET, inclusi C++ /CLI, consentono agli oggetti di generare eccezioni che non derivano da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="a6bc9-104">Tali eccezioni sono chiamate *eccezioni non CLS* o *non eccezioni*.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="a6bc9-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] non è possibile generare eccezioni non CLS, ma è possibile rilevarle in due modi:</span><span class="sxs-lookup"><span data-stu-id="a6bc9-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="a6bc9-106">All'interno di un blocco `catch (Exception e)` come oggetto <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="a6bc9-107">Per impostazione predefinita, un assembly [!INCLUDE[csprcs](~/includes/csprcs-md.md)] rileva le eccezioni non CLS come eccezioni con wrapper.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-107">By default, a [!INCLUDE[csprcs](~/includes/csprcs-md.md)] assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="a6bc9-108">Usare questo metodo se è necessario accedere all'eccezione originale, accessibile tramite la proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="a6bc9-109">La procedura illustrata più avanti in questo argomento spiega come rilevare le eccezioni in questo modo.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="a6bc9-110">All'interno di un blocco catch generale, ovvero un blocco catch senza un tipo di eccezione specificato, posizionato dopo un blocco `catch (Exception)` o `catch (Exception e)`.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="a6bc9-111">Usare questo metodo quando si vuole eseguire un'azione, come ad esempio la scrittura in un file di log, in risposta alle eccezioni non CLS e non è necessario accedere alle informazioni dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="a6bc9-112">Per impostazione predefinita, Common Language Runtime esegue il wrapping di tutte le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="a6bc9-113">Per disabilitare questo comportamento, aggiungere l'attributo a livello di assembly seguente al codice, in genere nel file AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="a6bc9-114">Per rilevare un'eccezione non CLS</span><span class="sxs-lookup"><span data-stu-id="a6bc9-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="a6bc9-115">All'interno di un oggetto `catch(Exception e) block` usare la parola chiave `as` per verificare se è possibile eseguire il cast di `e` a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="a6bc9-116">Accedere all'eccezione originale tramite la proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6bc9-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6bc9-117">Example</span></span>  
 <span data-ttu-id="a6bc9-118">Nell'esempio seguente viene illustrato come rilevare un'eccezione non CLS generata da una libreria di classi scritta in C++/CLR.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="a6bc9-119">Si noti che in questo esempio il codice client [!INCLUDE[csprcs](~/includes/csprcs-md.md)] sa in anticipo che il tipo di eccezione generato è <xref:System.String?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-119">Note that in this example, the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=fullName>.</span></span> <span data-ttu-id="a6bc9-120">È possibile eseguire il cast della proprietà <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> al tipo originale, a condizione che tale tipo sia accessibile dal codice.</span><span class="sxs-lookup"><span data-stu-id="a6bc9-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## <a name="see-also"></a><span data-ttu-id="a6bc9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6bc9-121">See Also</span></span>  
 <span data-ttu-id="a6bc9-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span><span class="sxs-lookup"><span data-stu-id="a6bc9-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span></span>   
 [<span data-ttu-id="a6bc9-123">Eccezioni e gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="a6bc9-123">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

