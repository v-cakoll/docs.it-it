---
title: Esposizione di componenti COM a .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230853abf73a368bfcd8b88375c216fdadfc7d46
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567268"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="f3c88-102">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3c88-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="f3c88-103">Questa sezione riepiloga il processo necessario per esporre un componente COM esistente al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f3c88-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="f3c88-104">Per informazioni dettagliate sulla scrittura di server COM strettamente integrati con .NET Framework, vedere [Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f3c88-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="f3c88-105">I componenti COM esistenti sono risorse preziose nel codice gestito come applicazioni aziendali di livello intermedio o come funzionalità isolate.</span><span class="sxs-lookup"><span data-stu-id="f3c88-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="f3c88-106">Un componente ideale ha un assembly di interoperabilità primario ed è strettamente conforme agli standard di programmazione imposti da COM.</span><span class="sxs-lookup"><span data-stu-id="f3c88-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="f3c88-107">Per esporre i componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3c88-107">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="f3c88-108">[Importare una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="f3c88-109">Common Language Runtime richiede metadati per tutti i tipi, inclusi i tipi COM.</span><span class="sxs-lookup"><span data-stu-id="f3c88-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="f3c88-110">Un assembly contenente tipi COM importati come metadati può essere ottenuto in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="f3c88-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="f3c88-111">[Usare i tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f3c88-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="f3c88-112">È possibile esaminare i tipi COM, attivare istanze e richiamare i metodi sull'oggetto COM esattamente come per gli altri tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="f3c88-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="f3c88-113">[Compilare un progetto di interoperabilità](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="f3c88-114">Windows SDK specifica i compilatori per diversi linguaggi conformi alle specifiche CLS, inclusi Visual Basic, C# e C++.</span><span class="sxs-lookup"><span data-stu-id="f3c88-114">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="f3c88-115">[Distribuire un'applicazione di interoperabilità](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="f3c88-116">Per una distribuzione ottimale delle applicazioni di interoperabilità, distribuirle come assembly firmati [con nome sicuro](../app-domains/strong-named-assemblies.md) nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="f3c88-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c88-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3c88-117">See also</span></span>

- [<span data-ttu-id="f3c88-118">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="f3c88-118">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="f3c88-119">[Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f3c88-119">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="f3c88-120">Esempio di interoperabilità COM: client .NET e server COM</span><span class="sxs-lookup"><span data-stu-id="f3c88-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="f3c88-121">Indipendenza del linguaggio e componenti indipendenti dal linguaggio</span><span class="sxs-lookup"><span data-stu-id="f3c88-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="f3c88-122">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="f3c88-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
