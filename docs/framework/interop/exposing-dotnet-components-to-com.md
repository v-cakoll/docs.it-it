---
title: Esposizione di componenti .NET a COM
description: Esporre i componenti .NET a COM. Qualifica i tipi .NET per l'interoperabilità. Applicare gli attributi di interoperabilità. Assemblare un assembly per COM. Utilizzare un tipo gestito da COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: 918c90f6741047f7d3cdf89a9b182700ecb2ed93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617458"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="0e7d7-107">Esposizione di componenti .NET a COM</span><span class="sxs-lookup"><span data-stu-id="0e7d7-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="0e7d7-108">La scrittura di un tipo .NET e l'utilizzo di tale tipo dal codice non gestito sono attività distinte per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="0e7d7-109">Questa sezione offre diversi suggerimenti per la scrittura di un codice gestito che interagisce con i client COM:</span><span class="sxs-lookup"><span data-stu-id="0e7d7-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="0e7d7-110">[Qualificazione di tipi .NET per l'interoperabilità](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="0e7d7-111">Tutti i tipi gestiti, i metodi, le proprietà, i campi e gli eventi che si vuole esporre a COM devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="0e7d7-112">I tipi devono avere un costruttore senza parametri pubblico, che è l'unico costruttore a poter essere richiamato tramite COM.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="0e7d7-113">[Applicazione degli attributi di interoperabilità](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="0e7d7-114">Gli attributi personalizzati nel codice gestito possono migliorare l'interoperabilità di un componente.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="0e7d7-115">Creazione [del pacchetto di un assembly per com](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="0e7d7-116">Gli sviluppatori COM potrebbero richiedere di riepilogare i passaggi previsti per fare riferimento agli assembly e distribuirli.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="0e7d7-117">Questa sezione indica anche le attività relative all'utilizzo di un tipo gestito da un client COM.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="0e7d7-118">Per utilizzare un tipo gestito da COM</span><span class="sxs-lookup"><span data-stu-id="0e7d7-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="0e7d7-119">[Registrare gli assembly con COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="0e7d7-120">I tipi in un assembly (e le librerie dei tipi) devono essere registrati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="0e7d7-121">Se un programma di installazione non registra l'assembly, comunicare agli sviluppatori COM di usare Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="0e7d7-122">[Fare riferimento a tipi .NET da com](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="0e7d7-123">Gli sviluppatori COM possono fare riferimento ai tipi in un assembly usando gli strumenti e le tecniche abituali.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="0e7d7-124">[Chiamare un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-124">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="0e7d7-125">Gli sviluppatori COM possono chiamare i metodi sull'oggetto .NET nello stesso modo in cui chiamano i metodi sui tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="0e7d7-126">Ad esempio, l'API **CoCreateInstance** COM attiva gli oggetti .NET.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="0e7d7-127">[Distribuire un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0e7d7-127">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="0e7d7-128">Un assembly con nome sicuro può essere installato nella Global Assembly Cache e richiede una firma dall'entità di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="0e7d7-129">Gli assembly privi di nome sicuro devono essere installati nella directory dell'applicazione del client.</span><span class="sxs-lookup"><span data-stu-id="0e7d7-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e7d7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e7d7-130">See also</span></span>

- [<span data-ttu-id="0e7d7-131">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="0e7d7-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="0e7d7-132">Esempio di interoperabilità COM: client COM e server .NET</span><span class="sxs-lookup"><span data-stu-id="0e7d7-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
