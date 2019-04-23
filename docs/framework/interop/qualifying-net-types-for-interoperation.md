---
title: Qualificazione di tipi .NET per l'interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cad67f52a4ca977606d7b5a307868ff129570e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097977"
---
# <a name="qualifying-net-types-for-interoperation"></a><span data-ttu-id="25325-102">Qualificazione di tipi .NET per l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="25325-102">Qualifying .NET Types for Interoperation</span></span>
<span data-ttu-id="25325-103">Se si vuole esporre i tipi contenuti in un assembly alle applicazioni COM, tenere presenti i requisiti di interoperabilità COM in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25325-103">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="25325-104">Rispettando le linee guida seguenti, è possibile ottenere una facile integrazione tra i tipi gestiti (classi, interfacce, strutture ed enumerazioni) e i tipi COM:</span><span class="sxs-lookup"><span data-stu-id="25325-104">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
-   <span data-ttu-id="25325-105">Le classi devono implementare le interfacce in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="25325-105">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="25325-106">Anche se l'interoperabilità COM fornisce un meccanismo per generare automaticamente un'interfaccia contenente tutti i membri della classe e i membri della relativa classe di base, è decisamente preferibile fornire interfacce esplicite.</span><span class="sxs-lookup"><span data-stu-id="25325-106">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="25325-107">L'interfaccia generata automaticamente è detta interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="25325-107">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="25325-108">Per informazioni, vedere [Introduzione all'interfaccia della classe](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="25325-108">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="25325-109">Per incorporare le definizioni di interfaccia nel codice, è possibile usare Visual Basic, C# e C++ invece del linguaggio di definizione dell'interfaccia (IDL, Interface Definition Language) o di soluzioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="25325-109">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="25325-110">Per informazioni dettagliate sulla sintassi, vedere la documentazione relativa al linguaggio.</span><span class="sxs-lookup"><span data-stu-id="25325-110">For syntax details, see your language documentation.</span></span>  
  
-   <span data-ttu-id="25325-111">I tipi gestiti devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="25325-111">Managed types must be public.</span></span>  
  
     <span data-ttu-id="25325-112">Solo i tipi pubblici di un assembly vengono registrati ed esportati nella libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="25325-112">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="25325-113">Di conseguenza, solo i tipi pubblici sono visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="25325-113">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="25325-114">I tipi gestiti espongono ad altro codice gestito funzionalità che potrebbero non essere esposte a COM.</span><span class="sxs-lookup"><span data-stu-id="25325-114">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="25325-115">Non vengono ad esempio esposti ai client COM i costruttori con parametri, i metodi statici e i campi costanti.</span><span class="sxs-lookup"><span data-stu-id="25325-115">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="25325-116">Poiché inoltre il runtime esegue il marshalling dei dati in entrata e in uscita da un tipo, è possibile che i dati vengano copiati o trasformati.</span><span class="sxs-lookup"><span data-stu-id="25325-116">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
-   <span data-ttu-id="25325-117">Metodi, proprietà, campi ed eventi devono essere pubblici.</span><span class="sxs-lookup"><span data-stu-id="25325-117">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="25325-118">Anche i membri dei tipi pubblici devono essere pubblici per essere visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="25325-118">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="25325-119">È possibile limitare la visibilità di un assembly, di un tipo pubblico o dei membri pubblici di un tipo pubblico applicando l'oggetto <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span><span class="sxs-lookup"><span data-stu-id="25325-119">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="25325-120">Per impostazione predefinita, tutti i membri e i tipi pubblici sono visibili.</span><span class="sxs-lookup"><span data-stu-id="25325-120">By default, all public types and members are visible.</span></span>  
  
-   <span data-ttu-id="25325-121">I tipi devono avere un costruttore pubblico predefinito per essere attivati da COM.</span><span class="sxs-lookup"><span data-stu-id="25325-121">Types must have a public default constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="25325-122">I tipi pubblici gestiti sono visibili in COM.</span><span class="sxs-lookup"><span data-stu-id="25325-122">Managed, public types are visible to COM.</span></span> <span data-ttu-id="25325-123">Senza un costruttore pubblico predefinito (un costruttore senza argomenti), tuttavia, i client COM non possono creare il tipo.</span><span class="sxs-lookup"><span data-stu-id="25325-123">However, without a public default constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="25325-124">I client COM possono comunque usare il tipo se viene attivato in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="25325-124">COM clients can still use the type if it is activated by some other means.</span></span>  
  
-   <span data-ttu-id="25325-125">I tipi non possono essere astratti.</span><span class="sxs-lookup"><span data-stu-id="25325-125">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="25325-126">Né i client COM né i client .NET possono creare tipi astratti.</span><span class="sxs-lookup"><span data-stu-id="25325-126">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="25325-127">Quando si esegue l'esportazione in COM, la gerarchia di ereditarietà di un tipo gestito viene appiattita.</span><span class="sxs-lookup"><span data-stu-id="25325-127">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="25325-128">Anche il controllo delle versioni varia tra ambiente gestito e ambiente non gestito.</span><span class="sxs-lookup"><span data-stu-id="25325-128">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="25325-129">I tipi esposti a COM non hanno le stesse caratteristiche di controllo delle versioni degli altri tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="25325-129">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25325-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25325-130">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="25325-131">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="25325-131">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="25325-132">Introduzione all'interfaccia della classe</span><span class="sxs-lookup"><span data-stu-id="25325-132">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="25325-133">Applicazione di attributi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="25325-133">Applying Interop Attributes</span></span>](../../../docs/framework/interop/applying-interop-attributes.md)
- [<span data-ttu-id="25325-134">Preparazione di un assembly per COM</span><span class="sxs-lookup"><span data-stu-id="25325-134">Packaging an Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
