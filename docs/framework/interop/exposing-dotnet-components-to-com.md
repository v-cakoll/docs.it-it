---
title: Esposizione di componenti .NET a COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4380e97cf4d556248f42981b350160710f1dd8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051814"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="67a77-102">Esposizione di componenti .NET a COM</span><span class="sxs-lookup"><span data-stu-id="67a77-102">Exposing .NET components to COM</span></span>

<span data-ttu-id="67a77-103">La scrittura di un tipo .NET e l'utilizzo di tale tipo dal codice non gestito sono attività distinte per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="67a77-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="67a77-104">Questa sezione offre diversi suggerimenti per la scrittura di un codice gestito che interagisce con i client COM:</span><span class="sxs-lookup"><span data-stu-id="67a77-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="67a77-105">[Qualificazione di tipi .NET per l'interoperabilità](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="67a77-105">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="67a77-106">Tutti i tipi gestiti, i metodi, le proprietà, i campi e gli eventi che si vuole esporre a COM devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="67a77-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="67a77-107">I tipi devono avere un costruttore senza parametri pubblico, che è l'unico costruttore a poter essere richiamato tramite COM.</span><span class="sxs-lookup"><span data-stu-id="67a77-107">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="67a77-108">[Applicazione di attributi di interoperabilità](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="67a77-108">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="67a77-109">Gli attributi personalizzati nel codice gestito possono migliorare l'interoperabilità di un componente.</span><span class="sxs-lookup"><span data-stu-id="67a77-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="67a77-110">[Preparazione di un assembly per COM](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="67a77-110">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="67a77-111">Gli sviluppatori COM potrebbero richiedere di riepilogare i passaggi previsti per fare riferimento agli assembly e distribuirli.</span><span class="sxs-lookup"><span data-stu-id="67a77-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="67a77-112">Questa sezione indica anche le attività relative all'utilizzo di un tipo gestito da un client COM.</span><span class="sxs-lookup"><span data-stu-id="67a77-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="67a77-113">Per utilizzare un tipo gestito da COM</span><span class="sxs-lookup"><span data-stu-id="67a77-113">To consume a managed type from COM</span></span>

1. <span data-ttu-id="67a77-114">[Registrare gli assembly con COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="67a77-114">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="67a77-115">I tipi in un assembly (e le librerie dei tipi) devono essere registrati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="67a77-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="67a77-116">Se un programma di installazione non registra l'assembly, comunicare agli sviluppatori COM di usare Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="67a77-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="67a77-117">[Fare riferimento a tipi .NET da COM](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="67a77-117">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="67a77-118">Gli sviluppatori COM possono fare riferimento ai tipi in un assembly usando gli strumenti e le tecniche abituali.</span><span class="sxs-lookup"><span data-stu-id="67a77-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="67a77-119">[Chiamare un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="67a77-119">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="67a77-120">Gli sviluppatori COM possono chiamare i metodi sull'oggetto .NET nello stesso modo in cui chiamano i metodi sui tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="67a77-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="67a77-121">Ad esempio, l'API **CoCreateInstance** COM attiva gli oggetti .NET.</span><span class="sxs-lookup"><span data-stu-id="67a77-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="67a77-122">[Distribuire un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="67a77-122">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="67a77-123">Un assembly con nome sicuro può essere installato nella Global Assembly Cache e richiede una firma dall'entità di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="67a77-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="67a77-124">Gli assembly privi di nome sicuro devono essere installati nella directory dell'applicazione del client.</span><span class="sxs-lookup"><span data-stu-id="67a77-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="67a77-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67a77-125">See also</span></span>

- [<span data-ttu-id="67a77-126">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="67a77-126">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="67a77-127">Esempio di interoperabilità COM: client COM e server .NET</span><span class="sxs-lookup"><span data-stu-id="67a77-127">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
