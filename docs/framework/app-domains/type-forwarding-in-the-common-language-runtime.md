---
title: Inoltro dei tipi in Common Language Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: c6e199800a86bc8b275fed4e3ba3ea6f77c7d2fa
ms.openlocfilehash: 2dad97aa9373f42e22690b0cc97de9d8c5b51d46
ms.contentlocale: it-it
ms.lasthandoff: 09/01/2017

---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="3ac6d-102">Inoltro dei tipi in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3ac6d-102">Type Forwarding in the Common Language Runtime</span></span>
<span data-ttu-id="3ac6d-103">L'inoltro dei tipi consente di spostare un tipo in un altro assembly senza dover ricompilare le applicazioni in cui viene utilizzato l'assembly originale.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="3ac6d-104">Si supponga ad esempio che in un'applicazione venga utilizzata la classe `Example` in un assembly denominato `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-104">For example, suppose an application uses the `Example` class in an assembly named `Utility.dll`.</span></span> <span data-ttu-id="3ac6d-105">Gli sviluppatori dell'assembly `Utility.dll` possono decidere di eseguire il refactoring dell'assembly e di spostare nel corso del processo la classe `Example` in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-105">The developers of `Utility.dll` might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="3ac6d-106">Se la versione precedente dell'assembly `Utility.dll` viene sostituita con la nuova versione dell'assembly `Utility.dll` e l'assembly complementare, l'applicazione in cui viene utilizzata la classe `Example` avrà esito negativo perché non è possibile trovare la classe `Example` nella nuova versione dell'assembly `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-106">If the old version of `Utility.dll` is replaced by the new version of `Utility.dll` and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of `Utility.dll`.</span></span>  
  
 <span data-ttu-id="3ac6d-107">Gli sviluppatori di `Utility.dll` possono evitare questo problema inoltrando le richieste per la classe `Example` mediante l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-107">The developers of `Utility.dll` can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="3ac6d-108">Se l'attributo è stato applicato alla nuova versione dell'assembly `Utility.dll`, le richieste della classe `Example` verranno inoltrate all'assembly in cui è ora contenuta la classe</span><span class="sxs-lookup"><span data-stu-id="3ac6d-108">If the attribute has been applied to the new version of `Utility.dll`, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="3ac6d-109">e l'applicazione esistente continuerà a funzionare normalmente, senza ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ac6d-110">In .NET Framework versione 2.0 non è possibile inoltrare i tipi da assembly scritti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="3ac6d-111">È tuttavia possibile utilizzare in un'applicazione scritta in Visual Basic tipi inoltrati,</span><span class="sxs-lookup"><span data-stu-id="3ac6d-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="3ac6d-112">ovvero se nell'applicazione viene utilizzato un assembly codificato in C# o C++ e un tipo di questo assembly viene inoltrato a un altro assembly, nell'applicazione Visual Basic sarà possibile utilizzare il tipo inoltrato.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forwarding-types"></a><span data-ttu-id="3ac6d-113">Inoltro di tipi</span><span class="sxs-lookup"><span data-stu-id="3ac6d-113">Forwarding Types</span></span>  
 <span data-ttu-id="3ac6d-114">La procedura di inoltro dei tipi prevede quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="3ac6d-114">There are four steps to forwarding a type:</span></span>  
  
1.  <span data-ttu-id="3ac6d-115">Spostare il codice sorgente del tipo dall'assembly originale nell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
  
2.  <span data-ttu-id="3ac6d-116">Nell'assembly in cui solitamente si trova il tipo usato, aggiungere un <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> per il tipo che è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="3ac6d-117">Nel codice riportato di seguito viene illustrato l'attributo per un tipo denominato `Example` che è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  <span data-ttu-id="3ac6d-118">Compilare l'assembly in cui è ora contenuto il tipo.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-118">Compile the assembly that now contains the type.</span></span>  
  
4.  <span data-ttu-id="3ac6d-119">Ricompilare l'assembly originale del tipo, con un riferimento all'assembly in cui è ora contenuto il tipo.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="3ac6d-120">Se ad esempio si compila un file C# dalla riga di comando, utilizzare l'opzione [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) per specificare l'assembly contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-120">For example, if you are compiling a C# file from the command line, use the [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="3ac6d-121">In C++ utilizzare la direttiva [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) nel file di origine per specificare l'assembly contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="3ac6d-121">In C++, use the [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac6d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac6d-122">See Also</span></span>  
 <span data-ttu-id="3ac6d-123"><xref:System.Runtime.CompilerServices.TypeForwardedToAttribute></span><span class="sxs-lookup"><span data-stu-id="3ac6d-123"><xref:System.Runtime.CompilerServices.TypeForwardedToAttribute></span></span>   
 <span data-ttu-id="3ac6d-124">[Inoltro del tipo (C++-CLI)](/cpp/windows/type-forwarding-cpp-cli) </span><span class="sxs-lookup"><span data-stu-id="3ac6d-124">[Type Forwarding (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli) </span></span>  
 [<span data-ttu-id="3ac6d-125">Direttiva #using</span><span class="sxs-lookup"><span data-stu-id="3ac6d-125">#using Directive</span></span>](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)

