---
title: 'Procedura: caricare assembly in un dominio applicazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: c560e2c5858de67442ccbcd18c8f92b142cc178d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119898"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="286c1-102">Procedura: caricare assembly in un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="286c1-102">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="286c1-103">È possibile caricare un assembly in un dominio dell'applicazione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="286c1-103">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="286c1-104">Il modo consigliato consiste nell'usare il metodo `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> della classe <xref:System.Reflection.Assembly?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="286c1-104">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="286c1-105">Gli assembly possono essere caricati anche nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="286c1-105">Other ways assemblies can be loaded include:</span></span>  
  
- <span data-ttu-id="286c1-106">Il metodo <xref:System.Reflection.Assembly.LoadFrom%2A> della classe <xref:System.Reflection.Assembly> carica un assembly dopo aver specificato il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="286c1-106">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="286c1-107">Se gli assembly vengono caricati usando questo metodo viene usato un contesto di caricamento diverso.</span><span class="sxs-lookup"><span data-stu-id="286c1-107">Loading assemblies with this method uses a different load context.</span></span>  
  
- <span data-ttu-id="286c1-108">I metodi <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> e <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> caricano un assembly nel contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="286c1-108">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="286c1-109">Gli assembly caricati in questo contesto possono essere esaminati ma non eseguiti. In questo modo è possibile esaminare assembly destinati ad altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="286c1-109">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="286c1-110">Vedere [How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Procedura: Caricare assembly nel contesto di sola reflection).</span><span class="sxs-lookup"><span data-stu-id="286c1-110">See [How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="286c1-111">Il contesto di sola reflection è stata introdotto con .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="286c1-111">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
- <span data-ttu-id="286c1-112">Metodi come <xref:System.AppDomain.CreateInstance%2A> e <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> della classe <xref:System.AppDomain> possono caricare gli assembly in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="286c1-112">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
- <span data-ttu-id="286c1-113">Il metodo <xref:System.Type.GetType%2A> della classe <xref:System.Type> può caricare assembly.</span><span class="sxs-lookup"><span data-stu-id="286c1-113">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
- <span data-ttu-id="286c1-114">Il metodo <xref:System.AppDomain.Load%2A> della classe <xref:System.AppDomain?displayProperty=nameWithType> può caricare assembly ma viene usato principalmente per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="286c1-114">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=nameWithType> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="286c1-115">Non usarlo per caricare assembly in un dominio dell'applicazione diverso da quello da cui è chiamato.</span><span class="sxs-lookup"><span data-stu-id="286c1-115">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="286c1-116">A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato.</span><span class="sxs-lookup"><span data-stu-id="286c1-116">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="286c1-117">Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="286c1-117">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="286c1-118">È possibile specificare la modalità di condivisione del codice con compilazione JIT degli assembly caricati tra i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="286c1-118">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="286c1-119">Per altre informazioni, vedere [Domini applicazione e assembly](application-domains.md#application-domains-and-assemblies).</span><span class="sxs-lookup"><span data-stu-id="286c1-119">For more information, see [Application domains and assemblies](application-domains.md#application-domains-and-assemblies).</span></span>  
  
## <a name="example"></a><span data-ttu-id="286c1-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="286c1-120">Example</span></span>  
 <span data-ttu-id="286c1-121">Il codice seguente carica un assembly denominato "example.exe" o "example.dll" nel dominio dell'applicazione corrente, ottiene un tipo denominato `Example` dall'assembly, ottiene un metodo senza parametri denominato `MethodA` per il tipo ed esegue il metodo.</span><span class="sxs-lookup"><span data-stu-id="286c1-121">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="286c1-122">Per una descrizione completa di come ottenere informazioni da un assembly caricato, vedere [Caricamento e uso dinamico dei tipi](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="286c1-122">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="286c1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="286c1-123">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [<span data-ttu-id="286c1-124">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="286c1-124">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="286c1-125">Reflection</span><span class="sxs-lookup"><span data-stu-id="286c1-125">Reflection</span></span>](../reflection-and-codedom/reflection.md)
- [<span data-ttu-id="286c1-126">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="286c1-126">Using Application Domains</span></span>](use.md)
- [<span data-ttu-id="286c1-127">Procedura: caricare assembly nel contesto Reflection-Only</span><span class="sxs-lookup"><span data-stu-id="286c1-127">How to: Load Assemblies into the Reflection-Only Context</span></span>](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [<span data-ttu-id="286c1-128">Domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="286c1-128">Application domains and assemblies</span></span>](application-domains.md#application-domains-and-assemblies)
