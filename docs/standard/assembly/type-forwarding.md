---
title: Inoltro dei tipi in Common Language Runtime
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 7b9fd4e89d1d3290dfc17f52de392c4ee9092d02
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138589"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="fd203-102">Inoltro dei tipi in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fd203-102">Type forwarding in the common language runtime</span></span>
<span data-ttu-id="fd203-103">L'inoltro dei tipi consente di spostare un tipo in un altro assembly senza dover ricompilare le applicazioni in cui viene utilizzato l'assembly originale.</span><span class="sxs-lookup"><span data-stu-id="fd203-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="fd203-104">Si supponga, ad esempio, che un'applicazione utilizzi la classe `Example` in un assembly denominato *Utility. dll*.</span><span class="sxs-lookup"><span data-stu-id="fd203-104">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="fd203-105">Gli sviluppatori di *Utility. dll* potrebbero decidere di effettuare il refactoring dell'assembly e nel processo potrebbero spostare la classe `Example` in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="fd203-105">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="fd203-106">Se la versione precedente di *Utility. dll* viene sostituita dalla nuova versione di *Utility. dll* e dall'assembly complementare, l'applicazione che usa la classe `Example` non riesce perché non è in grado di individuare la classe `Example` nella nuova versione di *Utility. dll* .</span><span class="sxs-lookup"><span data-stu-id="fd203-106">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="fd203-107">Gli sviluppatori di *Utility. dll* possono evitare questo problema tramite l'invio di richieste per la classe `Example`, usando l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd203-107">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="fd203-108">Se l'attributo è stato applicato alla nuova versione di *Utility. dll*, le richieste per la classe `Example` vengono inviate all'assembly che ora contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="fd203-108">If the attribute has been applied to the new version of *Utility.dll*, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="fd203-109">e l'applicazione esistente continuerà a funzionare normalmente, senza ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="fd203-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd203-110">In .NET Framework versione 2.0 non è possibile inoltrare i tipi da assembly scritti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fd203-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="fd203-111">È tuttavia possibile utilizzare in un'applicazione scritta in Visual Basic tipi inoltrati,</span><span class="sxs-lookup"><span data-stu-id="fd203-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="fd203-112">ovvero se nell'applicazione viene utilizzato un assembly codificato in C# o C++ e un tipo di questo assembly viene inoltrato a un altro assembly, nell'applicazione Visual Basic sarà possibile utilizzare il tipo inoltrato.</span><span class="sxs-lookup"><span data-stu-id="fd203-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forward-types"></a><span data-ttu-id="fd203-113">Tipi di inoltri</span><span class="sxs-lookup"><span data-stu-id="fd203-113">Forward types</span></span>  
 <span data-ttu-id="fd203-114">La procedura di inoltro dei tipi prevede quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="fd203-114">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="fd203-115">Spostare il codice sorgente del tipo dall'assembly originale nell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fd203-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
   
2. <span data-ttu-id="fd203-116">Nell'assembly in cui solitamente si trova il tipo usato, aggiungere un <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> per il tipo che è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="fd203-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="fd203-117">Nel codice riportato di seguito viene illustrato l'attributo per un tipo denominato `Example` che è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="fd203-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
   
   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```
   
   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  
   
3. <span data-ttu-id="fd203-118">Compilare l'assembly in cui è ora contenuto il tipo.</span><span class="sxs-lookup"><span data-stu-id="fd203-118">Compile the assembly that now contains the type.</span></span>  
   
4. <span data-ttu-id="fd203-119">Ricompilare l'assembly originale del tipo, con un riferimento all'assembly in cui è ora contenuto il tipo.</span><span class="sxs-lookup"><span data-stu-id="fd203-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="fd203-120">Se, ad esempio, si compila un C# file dalla riga di comando, utilizzare l'opzione [-Reference (C# opzioni del compilatore)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) per specificare l'assembly contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="fd203-120">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="fd203-121">In C++ utilizzare la direttiva [#using](/cpp/preprocessor/hash-using-directive-cpp) nel file di origine per specificare l'assembly contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="fd203-121">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd203-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd203-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="fd203-123">Invio del tipo (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="fd203-123">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="fd203-124">#using (direttiva)</span><span class="sxs-lookup"><span data-stu-id="fd203-124">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
