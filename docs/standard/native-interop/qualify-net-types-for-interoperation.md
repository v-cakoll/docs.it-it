---
title: Qualificazione di tipi .NET per l'interoperabilità COM
description: Questo articolo fornisce linee guida che consentono di esporre i tipi in un assembly .NET alle applicazioni COM per l'interoperabilità COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
ms.openlocfilehash: 5e8d604c8152d37475bf93e3b5687f24cfebfa02
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285963"
---
# <a name="qualifying-net-types-for-com-interoperation"></a><span data-ttu-id="83b9b-103">Qualificazione di tipi .NET per l'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="83b9b-103">Qualifying .NET Types for COM Interoperation</span></span>
<span data-ttu-id="83b9b-104">Se si vuole esporre i tipi contenuti in un assembly alle applicazioni COM, tenere presenti i requisiti di interoperabilità COM in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="83b9b-104">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="83b9b-105">Rispettando le linee guida seguenti, è possibile ottenere una facile integrazione tra i tipi gestiti (classi, interfacce, strutture ed enumerazioni) e i tipi COM:</span><span class="sxs-lookup"><span data-stu-id="83b9b-105">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
- <span data-ttu-id="83b9b-106">Le classi devono implementare le interfacce in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="83b9b-106">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="83b9b-107">Anche se l'interoperabilità COM fornisce un meccanismo per generare automaticamente un'interfaccia contenente tutti i membri della classe e i membri della relativa classe di base, è decisamente preferibile fornire interfacce esplicite.</span><span class="sxs-lookup"><span data-stu-id="83b9b-107">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="83b9b-108">L'interfaccia generata automaticamente è detta interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="83b9b-108">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="83b9b-109">Per le linee guida, vedere [Introduzione all'interfaccia della classe](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="83b9b-109">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="83b9b-110">Per incorporare le definizioni di interfaccia nel codice, è possibile usare Visual Basic, C# e C++ invece del linguaggio di definizione dell'interfaccia (IDL, Interface Definition Language) o di soluzioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="83b9b-110">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="83b9b-111">Per informazioni dettagliate sulla sintassi, vedere la documentazione relativa al linguaggio.</span><span class="sxs-lookup"><span data-stu-id="83b9b-111">For syntax details, see your language documentation.</span></span>  
  
- <span data-ttu-id="83b9b-112">I tipi gestiti devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="83b9b-112">Managed types must be public.</span></span>  
  
     <span data-ttu-id="83b9b-113">Solo i tipi pubblici di un assembly vengono registrati ed esportati nella libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="83b9b-113">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="83b9b-114">Di conseguenza, solo i tipi pubblici sono visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="83b9b-114">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="83b9b-115">I tipi gestiti espongono ad altro codice gestito funzionalità che potrebbero non essere esposte a COM.</span><span class="sxs-lookup"><span data-stu-id="83b9b-115">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="83b9b-116">Non vengono ad esempio esposti ai client COM i costruttori con parametri, i metodi statici e i campi costanti.</span><span class="sxs-lookup"><span data-stu-id="83b9b-116">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="83b9b-117">Poiché inoltre il runtime esegue il marshalling dei dati in entrata e in uscita da un tipo, è possibile che i dati vengano copiati o trasformati.</span><span class="sxs-lookup"><span data-stu-id="83b9b-117">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
- <span data-ttu-id="83b9b-118">Metodi, proprietà, campi ed eventi devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="83b9b-118">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="83b9b-119">Anche i membri dei tipi pubblici devono essere pubblici per essere visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="83b9b-119">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="83b9b-120">È possibile limitare la visibilità di un assembly, di un tipo pubblico o dei membri pubblici di un tipo pubblico applicando l'oggetto <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span><span class="sxs-lookup"><span data-stu-id="83b9b-120">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="83b9b-121">Per impostazione predefinita, tutti i membri e i tipi pubblici sono visibili.</span><span class="sxs-lookup"><span data-stu-id="83b9b-121">By default, all public types and members are visible.</span></span>  
  
- <span data-ttu-id="83b9b-122">I tipi devono avere un costruttore senza parametri pubblico per essere attivati da COM.</span><span class="sxs-lookup"><span data-stu-id="83b9b-122">Types must have a public parameterless constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="83b9b-123">I tipi pubblici gestiti sono visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="83b9b-123">Managed, public types are visible to COM.</span></span> <span data-ttu-id="83b9b-124">Senza un costruttore senza parametri pubblico (un costruttore senza argomenti), tuttavia, i client COM non possono creare il tipo.</span><span class="sxs-lookup"><span data-stu-id="83b9b-124">However, without a public parameterless constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="83b9b-125">I client COM possono comunque usare il tipo se viene attivato in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="83b9b-125">COM clients can still use the type if it is activated by some other means.</span></span>  
  
- <span data-ttu-id="83b9b-126">I tipi non possono essere astratti.</span><span class="sxs-lookup"><span data-stu-id="83b9b-126">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="83b9b-127">Né i client COM né i client .NET possono creare tipi astratti.</span><span class="sxs-lookup"><span data-stu-id="83b9b-127">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="83b9b-128">Quando si esegue l'esportazione in COM, la gerarchia di ereditarietà di un tipo gestito viene appiattita.</span><span class="sxs-lookup"><span data-stu-id="83b9b-128">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="83b9b-129">Anche il controllo delle versioni varia tra ambiente gestito e ambiente non gestito.</span><span class="sxs-lookup"><span data-stu-id="83b9b-129">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="83b9b-130">I tipi esposti a COM non hanno le stesse caratteristiche di controllo delle versioni degli altri tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="83b9b-130">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b9b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b9b-131">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="83b9b-132">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="83b9b-132">Exposing .NET Framework Components to COM</span></span>](../../framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="83b9b-133">Introduzione all'interfaccia della classe</span><span class="sxs-lookup"><span data-stu-id="83b9b-133">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="83b9b-134">Applicazione di attributi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="83b9b-134">Applying Interop Attributes</span></span>](apply-interop-attributes.md)
- [<span data-ttu-id="83b9b-135">Creazione di un pacchetto di un assembly .NET Framework per COM</span><span class="sxs-lookup"><span data-stu-id="83b9b-135">Packaging a .NET Framework Assembly for COM</span></span>](../../framework/interop/packaging-an-assembly-for-com.md)
