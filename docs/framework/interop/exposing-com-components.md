---
title: Esposizione di componenti COM a .NET Framework
description: Informazioni sul processo di esposizione dei componenti COM a .NET. I componenti COM sono utili nel codice gestito come applicazioni aziendali di livello intermedio o funzionalità isolate.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 459ba7ffed2e4f6c458f89a63b2baa37180d270d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620846"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="8a079-104">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8a079-104">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="8a079-105">Questa sezione riepiloga il processo necessario per esporre un componente COM esistente al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="8a079-105">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="8a079-106">Per informazioni dettagliate sulla scrittura di server COM strettamente integrati con .NET Framework, vedere [Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8a079-106">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="8a079-107">I componenti COM esistenti sono risorse preziose nel codice gestito come applicazioni aziendali di livello intermedio o come funzionalità isolate.</span><span class="sxs-lookup"><span data-stu-id="8a079-107">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="8a079-108">Un componente ideale ha un assembly di interoperabilità primario ed è strettamente conforme agli standard di programmazione imposti da COM.</span><span class="sxs-lookup"><span data-stu-id="8a079-108">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="8a079-109">Per esporre i componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8a079-109">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="8a079-110">[Importare una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="8a079-110">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="8a079-111">Common Language Runtime richiede metadati per tutti i tipi, inclusi i tipi COM.</span><span class="sxs-lookup"><span data-stu-id="8a079-111">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="8a079-112">Un assembly contenente tipi COM importati come metadati può essere ottenuto in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="8a079-112">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="8a079-113">[Usare i tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8a079-113">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="8a079-114">È possibile esaminare i tipi COM, attivare istanze e richiamare i metodi sull'oggetto COM esattamente come per gli altri tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="8a079-114">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="8a079-115">[Compilare un progetto di interoperabilità](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="8a079-115">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="8a079-116">Windows SDK specifica i compilatori per diversi linguaggi conformi alle specifiche CLS, inclusi Visual Basic, C# e C++.</span><span class="sxs-lookup"><span data-stu-id="8a079-116">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="8a079-117">[Distribuire un'applicazione di interoperabilità](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="8a079-117">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="8a079-118">Per una distribuzione ottimale delle applicazioni di interoperabilità, distribuirle come assembly firmati [con nome sicuro](../../standard/assembly/strong-named.md) nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="8a079-118">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a079-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a079-119">See also</span></span>

- [<span data-ttu-id="8a079-120">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="8a079-120">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="8a079-121">[Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8a079-121">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="8a079-122">Esempio di interoperabilità COM: client .NET e server COM</span><span class="sxs-lookup"><span data-stu-id="8a079-122">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="8a079-123">Indipendenza del linguaggio e componenti indipendenti dal linguaggio</span><span class="sxs-lookup"><span data-stu-id="8a079-123">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="8a079-124">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="8a079-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
