---
title: Creazione di un pacchetto di un assembly .NET Framework per COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
ms.openlocfilehash: 6866da283cc7cdd180aada252007d67bd72cd862
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124100"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a><span data-ttu-id="da84f-102">Creazione di un pacchetto di un assembly .NET Framework per COM</span><span class="sxs-lookup"><span data-stu-id="da84f-102">Packaging a .NET Framework Assembly for COM</span></span>

<span data-ttu-id="da84f-103">Gli sviluppatori COM possono trarre vantaggio dalle informazioni seguenti sui tipi gestiti che prevedono di incorporare nella propria applicazione:</span><span class="sxs-lookup"><span data-stu-id="da84f-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="da84f-104">Un elenco dei tipi utilizzabili dalle applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="da84f-104">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="da84f-105">Alcuni tipi gestiti non sono visibili per COM. Alcuni sono visibili, ma non generabili e alcuni sono sia visibili che generabili.</span><span class="sxs-lookup"><span data-stu-id="da84f-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="da84f-106">Un assembly può contenere qualsiasi combinazione di tipi invisibili, visibili, non generabili e generabili.</span><span class="sxs-lookup"><span data-stu-id="da84f-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="da84f-107">Per motivi di completezza, identificare i tipi in un assembly che si desidera esporre a COM, soprattutto quando tali tipi sono un subset dei tipi esposti a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da84f-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="da84f-108">Per altre informazioni, vedere [Qualificazione di tipi .NET per l'interoperabilità](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="da84f-108">For additional information, see [Qualifying .NET Types for Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="da84f-109">Istruzioni di controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="da84f-109">Versioning instructions</span></span>

  <span data-ttu-id="da84f-110">Le classi gestite che implementano l'interfaccia di classe (interfaccia generata dall'interoperabilità COM) sono soggette a restrizioni di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="da84f-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="da84f-111">Per linee guida sull'uso dell'interfaccia della classe, vedere [Introduzione all'interfaccia della classe](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="da84f-111">For guidelines on using the class interface, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="da84f-112">Istruzioni per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="da84f-112">Deployment instructions</span></span>

  <span data-ttu-id="da84f-113">Gli assembly con nome sicuro firmati da un editore possono essere installati nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="da84f-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="da84f-114">Gli assembly non firmati devono essere installati nel computer dell'utente come assembly privati.</span><span class="sxs-lookup"><span data-stu-id="da84f-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="da84f-115">Per altre informazioni, vedere [Considerazioni sulla sicurezza degli assembly](../../standard/assembly/security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="da84f-115">For additional information, see [Assembly Security Considerations](../../standard/assembly/security-considerations.md).</span></span>

- <span data-ttu-id="da84f-116">Inclusione di una libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="da84f-116">Type library inclusion</span></span>

  <span data-ttu-id="da84f-117">La maggior parte dei tipi richiede una libreria dei tipi per l'uso da un'applicazione COM.</span><span class="sxs-lookup"><span data-stu-id="da84f-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="da84f-118">È possibile generare una libreria dei tipi o delegare agli sviluppatori COM questa operazione.</span><span class="sxs-lookup"><span data-stu-id="da84f-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="da84f-119">Windows SDK include le opzioni seguenti per la generazione di una libreria dei tipi:</span><span class="sxs-lookup"><span data-stu-id="da84f-119">The Windows SDK provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="da84f-120">Utilità di esportazione della libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="da84f-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="da84f-121">Classe TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="da84f-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="da84f-122">Strumento di registrazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="da84f-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="da84f-123">Strumento di installazione dei servizi .NET</span><span class="sxs-lookup"><span data-stu-id="da84f-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="da84f-124">Indipendentemente dal meccanismo scelto, solo i tipi pubblici definiti nell'assembly specificato vengono inclusi nella libreria dei tipi generata.</span><span class="sxs-lookup"><span data-stu-id="da84f-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

<span data-ttu-id="da84f-125">Per istruzioni, vedere [Procedura: incorporare librerie dei tipi come risorse Win32 nelle applicazioni basate su .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="da84f-125">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="da84f-126">Utilità di esportazione della libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="da84f-126">Type Library Exporter</span></span>

<span data-ttu-id="da84f-127">[Tlbexp.exe (utilità di esportazione della libreria dei tipi)](../tools/tlbexp-exe-type-library-exporter.md) è uno strumento da riga di comando che converte le classi e le interfacce contenute in un assembly in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="da84f-127">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="da84f-128">Quando le informazioni sui tipi della classe sono disponibili, i client COM possono creare un'istanza della classe .NET e chiamare i metodi dell'istanza, come se si trattasse di un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="da84f-128">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="da84f-129">Tlbexp.exe converte un intero assembly in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="da84f-129">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="da84f-130">Non è possibile utilizzare Tlbexp.exe per generare informazioni sui tipi per un sottoinsieme dei tipi definiti in un assembly.</span><span class="sxs-lookup"><span data-stu-id="da84f-130">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="da84f-131">Classe TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="da84f-131">TypeLibConverter Class</span></span>

<span data-ttu-id="da84f-132">La classe <xref:System.Runtime.InteropServices.TypeLibConverter>, inclusa nello spazio dei nomi **System.Runtime.Interop**, converte le classi e interfacce contenute in un assembly in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="da84f-132">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="da84f-133">Questa API genera le stesse informazioni sui tipi dell'utilità di esportazione della libreria dei tipi, descritta nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="da84f-133">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="da84f-134">La **classe TypeLibConverter** implementa <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="da84f-134">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="da84f-135">Strumento di registrazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="da84f-135">Assembly Registration Tool</span></span>

<span data-ttu-id="da84f-136">Lo [strumento di registrazione degli assembly (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) può generare e registrare una libreria dei tipi quando si applica l'opzione **/tlb:**.</span><span class="sxs-lookup"><span data-stu-id="da84f-136">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="da84f-137">I client COM richiedono l'installazione di librerie dei tipi nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="da84f-137">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="da84f-138">Senza questa opzione, Regasm.exe registra solo i tipi in un assembly, non la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="da84f-138">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="da84f-139">Registrare i tipi in un assembly e la registrazione della libreria dei tipi sono due attività distinte.</span><span class="sxs-lookup"><span data-stu-id="da84f-139">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="da84f-140">Strumento di installazione dei servizi .NET</span><span class="sxs-lookup"><span data-stu-id="da84f-140">.NET Services Installation Tool</span></span>

<span data-ttu-id="da84f-141">Lo [strumento di installazione dei servizi .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) aggiunge classi gestite ai servizi componenti di Windows 2000 e combina diverse attività in un unico strumento.</span><span class="sxs-lookup"><span data-stu-id="da84f-141">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="da84f-142">Oltre a caricamento e registrazione di un assembly, Regsvcs.exe può generare, registrare e installare la libreria dei tipi in un'applicazione COM+ 1.0 esistente.</span><span class="sxs-lookup"><span data-stu-id="da84f-142">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="da84f-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da84f-143">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="da84f-144">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="da84f-144">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="da84f-145">Qualificazione di tipi .NET per l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="da84f-145">Qualifying .NET Types for Interoperation</span></span>](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="da84f-146">Introduzione all'interfaccia della classe</span><span class="sxs-lookup"><span data-stu-id="da84f-146">Introducing the class interface</span></span>](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="da84f-147">Considerazioni sulla sicurezza degli assembly</span><span class="sxs-lookup"><span data-stu-id="da84f-147">Assembly Security Considerations</span></span>](../../standard/assembly/security-considerations.md)
- [<span data-ttu-id="da84f-148">Tlbexp. exe (utilità di esportazione della libreria di tipi)</span><span class="sxs-lookup"><span data-stu-id="da84f-148">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="da84f-149">Registrazione di assembly presso COM</span><span class="sxs-lookup"><span data-stu-id="da84f-149">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="da84f-150">[Procedura: incorporare librerie dei tipi come risorse Win32 nelle applicazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="da84f-150">[How to: Embed Type Libraries as Win32 Resources in Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>
