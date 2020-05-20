---
title: COM Callable Wrapper
description: Quando un client COM chiama un oggetto .NET, CLR crea l'oggetto gestito e un COM Callable Wrapper. I client COM chiamano il wrapper per l'oggetto.
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
ms.openlocfilehash: c42ea0b5ba4cb01304ceae4ba2d2fc91b629a9b3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420526"
---
# <a name="com-callable-wrapper"></a><span data-ttu-id="6c9c0-104">COM Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="6c9c0-104">COM Callable Wrapper</span></span>

<span data-ttu-id="6c9c0-105">Quando un client COM chiama un oggetto .NET, Common Language Runtime crea l'oggetto gestito e un COM Callable Wrapper (CCW) per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-105">When a COM client calls a .NET object, the common language runtime creates the managed object and a COM callable wrapper (CCW) for the object.</span></span> <span data-ttu-id="6c9c0-106">Incapaci di fare riferimento diretto a un oggetto .NET, i client COM usano il CCW come un proxy per l'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-106">Unable to reference a .NET object directly, COM clients use the CCW as a proxy for the managed object.</span></span>

<span data-ttu-id="6c9c0-107">Il runtime crea esattamente un CCW per ciascun oggetto gestito, indipendentemente dal numero di client COM che ne richiedono i servizi.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-107">The runtime creates exactly one CCW for a managed object, regardless of the number of COM clients requesting its services.</span></span> <span data-ttu-id="6c9c0-108">Come mostrato nella figura seguente, più client COM possono mantenere un riferimento allo stesso CCW che espone l'interfaccia INew.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-108">As the following illustration shows, multiple COM clients can hold a reference to the CCW that exposes the INew interface.</span></span> <span data-ttu-id="6c9c0-109">Il CCW mantiene a sua volta un solo riferimento all'oggetto gestito che implementa l'interfaccia ed è sottoposto alla procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-109">The CCW, in turn, holds a single reference to the managed object that implements the interface and is garbage collected.</span></span> <span data-ttu-id="6c9c0-110">Sia i client COM che i client .NET possono effettuare contemporaneamente richieste sullo stesso oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-110">Both COM and .NET clients can make requests on the same managed object simultaneously.</span></span>

![Più client COM contenenti un riferimento al CCW che espone INew.](./media/com-callable-wrapper/com-callable-wrapper-clients.gif)

<span data-ttu-id="6c9c0-112">Gli oggetti COM Callable Wrapper sono invisibili alle altre classi in esecuzione nel runtime .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-112">COM callable wrappers are invisible to other classes running within the .NET runtime.</span></span> <span data-ttu-id="6c9c0-113">Il loro scopo principale è effettuare il marshalling delle chiamate tra il codice gestito e quello non gestito. Tuttavia, i CCW gestiscono anche l'identità e la durata degli oggetti gestiti di cui eseguono il wrapping.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-113">Their primary purpose is to marshal calls between managed and unmanaged code; however, CCWs also manage the object identity and object lifetime of the managed objects they wrap.</span></span>

## <a name="object-identity"></a><span data-ttu-id="6c9c0-114">Identità dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="6c9c0-114">Object Identity</span></span>

<span data-ttu-id="6c9c0-115">Il runtime alloca per l'oggetto .NET memoria attinta dall'heap sottoposto a Garbage Collection. In tal modo si consente al runtime di spostare l'oggetto in memoria a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-115">The runtime allocates memory for the .NET object from its garbage-collected heap, which enables the runtime to move the object around in memory as necessary.</span></span> <span data-ttu-id="6c9c0-116">Al contrario, il runtime alloca per il CCW memoria attinta da un heap non soggetto a Garbage Collection, consentendo così ai client COM di fare riferimento al wrapper direttamente.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-116">In contrast, the runtime allocates memory for the CCW from a noncollected heap, making it possible for COM clients to reference the wrapper directly.</span></span>

## <a name="object-lifetime"></a><span data-ttu-id="6c9c0-117">Durata dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="6c9c0-117">Object Lifetime</span></span>

<span data-ttu-id="6c9c0-118">Diversamente dal client .NET di cui esegue il wrapping, il CCW è destinatario di riferimenti conteggiati in modo tradizionale (COM).</span><span class="sxs-lookup"><span data-stu-id="6c9c0-118">Unlike the .NET client it wraps, the CCW is reference-counted in traditional COM fashion.</span></span> <span data-ttu-id="6c9c0-119">Quando il conteggio dei riferimenti al CCW raggiunge lo zero, il wrapper rilascia il proprio riferimento all'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-119">When the reference count on the CCW reaches zero, the wrapper releases its reference on the managed object.</span></span> <span data-ttu-id="6c9c0-120">Gli oggetti gestiti senza più riferimenti vengono raccolti durante la successiva procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-120">A managed object with no remaining references is collected during the next garbage-collection cycle.</span></span>

## <a name="simulating-com-interfaces"></a><span data-ttu-id="6c9c0-121">Simulazione di interfacce COM</span><span class="sxs-lookup"><span data-stu-id="6c9c0-121">Simulating COM interfaces</span></span>

<span data-ttu-id="6c9c0-122">CCW espone ai client COM tutti i tipi di dati, i valori restituiti e le interfacce pubbliche visibili a COM in modo conforme al meccanismo di interazione COM basato sulle interfacce.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-122">CCW exposes all public, COM-visible interfaces, data types, and return values to COM clients in a manner that is consistent with COM's enforcement of interface-based interaction.</span></span> <span data-ttu-id="6c9c0-123">Per un client COM, richiamare i metodi in un oggetto .NET equivale a richiamarli in un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-123">For a COM client, invoking methods on a .NET object is identical to invoking methods on a COM object.</span></span>

<span data-ttu-id="6c9c0-124">Per assicurare questo approccio naturale, il CCW crea interfacce COM tradizionali quali **IUnknown** e **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-124">To create this seamless approach, the CCW manufactures traditional COM interfaces, such as **IUnknown** and **IDispatch**.</span></span> <span data-ttu-id="6c9c0-125">Come mostrato nella figura seguente, il CCW mantiene un solo riferimento all'oggetto .NET di cui esegue il wrapping.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-125">As the following illustration shows, the CCW maintains a single reference on the .NET object that it wraps.</span></span> <span data-ttu-id="6c9c0-126">Il client COM e l'oggetto .NET interagiscono tramite il proxy e lo stub del CCW.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-126">Both the COM client and the .NET object interact with each other through the proxy and stub construction of the CCW.</span></span>

![Diagramma che mostra come CCW crea interfacce COM.](./media/com-callable-wrapper/com-callable-wrapper-interfaces.gif)

<span data-ttu-id="6c9c0-128">Oltre a esporre le interfacce che sono esplicitamente implementate da una classe dell'ambiente gestito, il runtime .NET fornisce le implementazioni delle interfacce COM elencate nella tabella seguente per conto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-128">In addition to exposing the interfaces that are explicitly implemented by a class in the managed environment, the .NET runtime supplies implementations of the COM interfaces listed in the following table on behalf of the object.</span></span> <span data-ttu-id="6c9c0-129">Una classe .NET può eseguire l'override del comportamento predefinito fornendo la propria implementazione di queste interfacce.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-129">A .NET class can override the default behavior by providing its own implementation of these interfaces.</span></span> <span data-ttu-id="6c9c0-130">Il runtime, tuttavia, fornisce sempre l'implementazione delle interfacce **IUnknown** e **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-130">However, the runtime always provides the implementation for the **IUnknown** and **IDispatch** interfaces.</span></span>

|<span data-ttu-id="6c9c0-131">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="6c9c0-131">Interface</span></span>|<span data-ttu-id="6c9c0-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c9c0-132">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="6c9c0-133">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-133">**IDispatch**</span></span>|<span data-ttu-id="6c9c0-134">Fornisce un meccanismo per l'associazione tardiva al tipo.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-134">Provides a mechanism for late binding to type.</span></span>|
|<span data-ttu-id="6c9c0-135">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-135">**IErrorInfo**</span></span>|<span data-ttu-id="6c9c0-136">Fornisce una descrizione testuale dell'errore, la relativa origine, un file della Guida, un contesto della Guida e il GUID dell'interfaccia che ha definito l'errore (sempre **GUID_NULL** per le classi .NET).</span><span class="sxs-lookup"><span data-stu-id="6c9c0-136">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|
|<span data-ttu-id="6c9c0-137">**IProvideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-137">**IProvideClassInfo**</span></span>|<span data-ttu-id="6c9c0-138">Consente ai client COM di ottenere l'accesso all'interfaccia **ITypeInfo** implementata da una classe gestita.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-138">Enables COM clients to gain access to the **ITypeInfo** interface implemented by a managed class.</span></span> <span data-ttu-id="6c9c0-139">Restituisce `COR_E_NOTSUPPORTED` in .NET Core per i tipi non importati da COM.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-139">Returns `COR_E_NOTSUPPORTED` on .NET Core for types not imported from COM.</span></span> |
|<span data-ttu-id="6c9c0-140">**ISupportErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-140">**ISupportErrorInfo**</span></span>|<span data-ttu-id="6c9c0-141">Consente a un client COM di determinare se l'oggetto gestito supporta l'interfaccia **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-141">Enables a COM client to determine whether the managed object supports the **IErrorInfo** interface.</span></span> <span data-ttu-id="6c9c0-142">Se sì, consente al client di ottenere un puntatore all'ultimo oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-142">If so, enables the client to obtain a pointer to the latest exception object.</span></span> <span data-ttu-id="6c9c0-143">Tutti i tipi gestiti supportano l'interfaccia **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-143">All managed types support the **IErrorInfo** interface.</span></span>|
|<span data-ttu-id="6c9c0-144">**ITypeInfo** (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="6c9c0-144">**ITypeInfo** (.NET Framework Only)</span></span>|<span data-ttu-id="6c9c0-145">Fornisce per le classi le stesse informazioni sul tipo che fornisce Tlbexp.exe.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-145">Provides type information for a class that is exactly the same as the type information produced by Tlbexp.exe.</span></span>|
|<span data-ttu-id="6c9c0-146">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-146">**IUnknown**</span></span>|<span data-ttu-id="6c9c0-147">Fornisce l'implementazione standard dell'interfaccia **IUnknown** con cui il client COM gestisce la durata del CCW e provvede alla coercizione dei tipi.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-147">Provides the standard implementation of the **IUnknown** interface with which the COM client manages the lifetime of the CCW and provides type coercion.</span></span>|

 <span data-ttu-id="6c9c0-148">Le classi gestite possono anche fornire le interfacce COM descritte nella tabella che segue.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-148">A managed class can also provide the COM interfaces described in the following table.</span></span>

|<span data-ttu-id="6c9c0-149">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="6c9c0-149">Interface</span></span>|<span data-ttu-id="6c9c0-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c9c0-150">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="6c9c0-151">Interfaccia della \_ classe (*NomeClasse*)</span><span class="sxs-lookup"><span data-stu-id="6c9c0-151">The (\_*classname*) class interface</span></span>|<span data-ttu-id="6c9c0-152">Interfaccia, esposta dal runtime e non definita esplicitamente, che espone tutte le interfacce, i metodi, le proprietà e i campi pubblici esplicitamente esposti su un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-152">Interface, exposed by the runtime and not explicitly defined, that exposes all public interfaces, methods, properties, and fields that are explicitly exposed on a managed object.</span></span>|
|<span data-ttu-id="6c9c0-153">**IConnectionPoint** e **IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-153">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="6c9c0-154">Interfaccia per oggetti che originano eventi basati su delegati (un'interfaccia per la registrazione di sottoscrittori di eventi).</span><span class="sxs-lookup"><span data-stu-id="6c9c0-154">Interface for objects that source delegate-based events (an interface for registering event subscribers).</span></span>|
|<span data-ttu-id="6c9c0-155">**IDispatchEx** (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="6c9c0-155">**IDispatchEx** (.NET Framework Only)</span></span>|<span data-ttu-id="6c9c0-156">Interfaccia fornita dal runtime se la classe implementa **IExpando**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-156">Interface supplied by the runtime if the class implements **IExpando**.</span></span> <span data-ttu-id="6c9c0-157">L'interfaccia **IDispatchEx** è un'estensione dell'interfaccia **IDispatch** che, diversamente da **IDispatch**, consente l'enumerazione, l'aggiunta, l'eliminazione e la chiamata dei membri con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-157">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch**, enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|
|<span data-ttu-id="6c9c0-158">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="6c9c0-158">**IEnumVARIANT**</span></span>|<span data-ttu-id="6c9c0-159">Interfaccia per classi Collection che enumera gli oggetti della raccolta se la classe implementa **IEnumerable**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-159">Interface for collection-type classes, which enumerates the objects in the collection if the class implements **IEnumerable**.</span></span>|

## <a name="introducing-the-class-interface"></a><span data-ttu-id="6c9c0-160">Introduzione all'interfaccia della classe</span><span class="sxs-lookup"><span data-stu-id="6c9c0-160">Introducing the class interface</span></span>

<span data-ttu-id="6c9c0-161">L'interfaccia della classe, che non è definita esplicitamente nel codice gestito, è un'interfaccia che espone tutte le proprietà, i campi, gli eventi e i metodi pubblici esplicitamente esposti dall'oggetto .NET.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-161">The class interface, which is not explicitly defined in managed code, is an interface that exposes all public methods, properties, fields, and events that are explicitly exposed on the .NET object.</span></span> <span data-ttu-id="6c9c0-162">Tale interfaccia può essere duale o solo dispatch.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-162">This interface can be a dual or dispatch-only interface.</span></span> <span data-ttu-id="6c9c0-163">L'interfaccia della classe riceve il nome dalla classe .NET stessa, preceduto da un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-163">The class interface receives the name of the .NET class itself, preceded by an underscore.</span></span> <span data-ttu-id="6c9c0-164">Per la classe Mammal, ad esempio, l'interfaccia della classe sarà \_Mammal.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-164">For example, for class Mammal, the class interface is \_Mammal.</span></span>

<span data-ttu-id="6c9c0-165">Per le classi derivate, l'interfaccia della classe espone anche tutti i metodi, le proprietà e i campi pubblici della classe base.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-165">For derived classes, the class interface also exposes all public methods, properties, and fields of the base class.</span></span> <span data-ttu-id="6c9c0-166">La classe derivata espone anche un'interfaccia della classe per ciascuna classe base.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-166">The derived class also exposes a class interface for each base class.</span></span> <span data-ttu-id="6c9c0-167">Ad esempio, se la classe Mammal estende la classe MammalSuperclass, che a sua volta estende la classe System.Object, l'oggetto .NET espone ai client COM tre interfacce della classe denominate \_Mammal, \_MammalSuperclass e \_Object.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-167">For example, if class Mammal extends class MammalSuperclass, which itself extends System.Object, the .NET object exposes to COM clients three class interfaces named \_Mammal, \_MammalSuperclass, and \_Object.</span></span>

<span data-ttu-id="6c9c0-168">Si consideri ad esempio la classe .NET seguente:</span><span class="sxs-lookup"><span data-stu-id="6c9c0-168">For example, consider the following .NET class:</span></span>

```vb
' Applies the ClassInterfaceAttribute to set the interface to dual.
<ClassInterface(ClassInterfaceType.AutoDual)> _
' Implicitly extends System.Object.
Public Class Mammal
    Sub Eat()
    Sub Breathe()
    Sub Sleep()
End Class
```

```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```

<span data-ttu-id="6c9c0-169">Il client COM può ottenere un puntatore a un'interfaccia di classe denominata `_Mammal`.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-169">The COM client can obtain a pointer to a class interface named `_Mammal`.</span></span> <span data-ttu-id="6c9c0-170">In .NET Framework è possibile usare l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) per generare una libreria dei tipi contenente la definizione dell'interfaccia `_Mammal`.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-170">On .NET Framework, you can use the [Type Library Exporter (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) tool to generate a type library containing the `_Mammal` interface definition.</span></span> <span data-ttu-id="6c9c0-171">L'utilità di esportazione della libreria dei tipi non è supportata in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-171">The Type Library Exporter is not supported on .NET Core.</span></span> <span data-ttu-id="6c9c0-172">Se la classe `Mammal` implementa una o più interfacce, queste appariranno sotto la coclasse.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-172">If the `Mammal` class implemented one or more interfaces, the interfaces would appear under the coclass.</span></span>

```console
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]
interface _Mammal : IDispatch
{
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*
        pRetVal);
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]
        VARIANT_BOOL* pRetVal);
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);
    [id(0x6002000d)] HRESULT Eat();
    [id(0x6002000e)] HRESULT Breathe();
    [id(0x6002000f)] HRESULT Sleep();
}
[uuid(…)]
coclass Mammal
{
    [default] interface _Mammal;
}
```

<span data-ttu-id="6c9c0-173">La generazione dell'interfaccia della classe è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-173">Generating the class interface is optional.</span></span> <span data-ttu-id="6c9c0-174">Per impostazione predefinita, l'interoperabilità COM genera un'interfaccia solo dispatch per ogni classe esportata in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-174">By default, COM interop generates a dispatch-only interface for each class you export to a type library.</span></span> <span data-ttu-id="6c9c0-175">È possibile modificare o impedire la creazione automatica di questa interfaccia applicando alla classe l'oggetto <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-175">You can prevent or modify the automatic creation of this interface by applying the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> to your class.</span></span> <span data-ttu-id="6c9c0-176">Benché l'interfaccia della classe possa semplificare l'esposizione di classi gestite a COM, gli usi che è possibile farne sono limitati.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-176">Although the class interface can ease the task of exposing managed classes to COM, its uses are limited.</span></span>

> [!CAUTION]
> <span data-ttu-id="6c9c0-177">Usare l'interfaccia della classe, anziché definire esplicitamente un'interfaccia personalizzata, può complicare il futuro controllo delle versioni della classe gestita.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-177">Using the class interface, instead of explicitly defining your own, can complicate the future versioning of your managed class.</span></span> <span data-ttu-id="6c9c0-178">Prima di usare l'interfaccia della classe, leggere le indicazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-178">Please read the following guidelines before using the class interface.</span></span>

### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a><span data-ttu-id="6c9c0-179">Definire un'interfaccia esplicita per i client COM anziché generare l'interfaccia della classe.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-179">Define an explicit interface for COM clients to use rather than generating the class interface.</span></span>

<span data-ttu-id="6c9c0-180">Poiché l'interoperabilità COM genera l'interfaccia della classe automaticamente, le modifiche apportate alla classe dopo l'emissione di una versione possono alterare il layout dell'interfaccia della classe esposta da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-180">Because COM interop generates a class interface automatically, post-version changes to your class can alter the layout of the class interface exposed by the common language runtime.</span></span> <span data-ttu-id="6c9c0-181">Se si cambia il layout dei membri della classe, la maggior parte dei client COM, che solitamente non è in grado di gestire le modifiche al layout di un'interfaccia, cesserà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-181">Since COM clients are typically unprepared to handle changes in the layout of an interface, they break if you change the member layout of the class.</span></span>

<span data-ttu-id="6c9c0-182">Queste indicazioni ribadiscono il concetto che le interfacce esposte ai client COM devono restare immodificabili.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-182">This guideline reinforces the notion that interfaces exposed to COM clients must remain unchangeable.</span></span> <span data-ttu-id="6c9c0-183">Per ridurre il rischio di compromettere il funzionamento dei client COM riordinando inavvertitamente il layout dell'interfaccia, separare tutte le modifiche alla classe dal layout dell'interfaccia definendo esplicitamente le interfacce.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-183">To reduce the risk of breaking COM clients by inadvertently reordering the interface layout, isolate all changes to the class from the interface layout by explicitly defining interfaces.</span></span>

<span data-ttu-id="6c9c0-184">Usare **ClassInterfaceAttribute** per disattivare la generazione automatica dell'interfaccia della classe e implementare un'interfaccia esplicita per la classe, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6c9c0-184">Use the **ClassInterfaceAttribute** to disengage the automatic generation of the class interface and implement an explicit interface for the class, as the following code fragment shows:</span></span>

```vb
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp
    Implements IExplicit
    Sub M() Implements IExplicit.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```

<span data-ttu-id="6c9c0-185">Il valore **ClassInterfaceType.None** impedisce la generazione dell'interfaccia della classe quando i metadati della classe vengono esportati in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-185">The **ClassInterfaceType.None** value prevents the class interface from being generated when the class metadata is exported to a type library.</span></span> <span data-ttu-id="6c9c0-186">Nel precedente esempio, i client COM possono accedere alla classe `LoanApp` solo tramite l'interfaccia `IExplicit`.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-186">In the preceding example, COM clients can access the `LoanApp` class only through the `IExplicit` interface.</span></span>

### <a name="avoid-caching-dispatch-identifiers-dispids"></a><span data-ttu-id="6c9c0-187">Evitare la memorizzazione nella cache degli identificatori dispatch (DispId)</span><span class="sxs-lookup"><span data-stu-id="6c9c0-187">Avoid caching dispatch identifiers (DispIds)</span></span>

<span data-ttu-id="6c9c0-188">L'uso dell'interfaccia della classe è ammissibile per i client basati su script, i client Microsoft Visual Basic 6.0 o qualsiasi client ad associazione tardiva che non inserisce nella cache i DispId dei membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-188">Using the class interface is an acceptable option for scripted clients, Microsoft Visual Basic 6.0 clients, or any late-bound client that does not cache the DispIds of interface members.</span></span> <span data-ttu-id="6c9c0-189">I DispId identificano i membri di interfaccia per abilitare l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-189">DispIds identify interface members to enable late binding.</span></span>

<span data-ttu-id="6c9c0-190">Per l'interfaccia della classe, la generazione dei DispId è basata sulla posizione dei membri nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-190">For the class interface, generation of DispIds is based on the position of the member in the interface.</span></span> <span data-ttu-id="6c9c0-191">Se si cambia l'ordine dei membri e si esporta la classe in una libreria dei tipi, si altereranno i DispId generati nell'interfaccia della classe.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-191">If you change the order of the member and export the class to a type library, you will alter the DispIds generated in the class interface.</span></span>

<span data-ttu-id="6c9c0-192">Per evitare di compromettere il funzionamento dei client COM ad associazione tardiva quando si usa questa interfaccia, applicare **ClassInterfaceAttribute** con il valore **ClassInterfaceType.AutoDispatch**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-192">To avoid breaking late-bound COM clients when using the class interface, apply the **ClassInterfaceAttribute** with the **ClassInterfaceType.AutoDispatch** value.</span></span> <span data-ttu-id="6c9c0-193">Tale valore implementa un'interfaccia della classe solo dispatch, ma omette la descrizione dell'interfaccia dalla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-193">This value implements a dispatch-only class interface, but omits the interface description from the type library.</span></span> <span data-ttu-id="6c9c0-194">Senza una descrizione dell'interfaccia, i client non potranno inserire i DispId nella cache in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-194">Without an interface description, clients are unable to cache DispIds at compile time.</span></span> <span data-ttu-id="6c9c0-195">Benché questo sia il tipo di interfaccia predefinito per l'interfaccia della classe, è possibile applicare il valore dell'attributo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-195">Although this is the default interface type for the class interface, you can apply the attribute value explicitly.</span></span>

```vb
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp
    Implements IAnother
    Sub M() Implements IAnother.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```

<span data-ttu-id="6c9c0-196">Per ottenere il DispId di un membro di interfaccia in fase di esecuzione, i client COM possono chiamare **IDispatch.GetIdsOfNames**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-196">To get the DispId of an interface member at run time, COM clients can call **IDispatch.GetIdsOfNames**.</span></span> <span data-ttu-id="6c9c0-197">Per richiamare un metodo sull'interfaccia, passare il DispId restituito come argomento a **IDispatch.Invoke**.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-197">To invoke a method on the interface, pass the returned DispId as an argument to **IDispatch.Invoke**.</span></span>

### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a><span data-ttu-id="6c9c0-198">Limitare l'uso dell'opzione di interfaccia duale per l'interfaccia della classe.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-198">Restrict using the dual interface option for the class interface.</span></span>

<span data-ttu-id="6c9c0-199">Le interfacce duali permettono ai client COM di effettuare sia l'associazione anticipata che l'associazione tardiva ai membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-199">Dual interfaces enable early and late binding to interface members by COM clients.</span></span> <span data-ttu-id="6c9c0-200">In fase di progettazione e durante il test, può risultare utile impostare l'interfaccia della classe su duale.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-200">At design time and during testing, you might find it useful to set the class interface to dual.</span></span> <span data-ttu-id="6c9c0-201">Per una classe gestita (e le relative classi base) che non verrà mai modificata, questa opzione è accettabile.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-201">For a managed class (and its base classes) that will never be modified, this option is also acceptable.</span></span> <span data-ttu-id="6c9c0-202">In tutti gli altri casi è preferibile evitare di impostare l'interfaccia della classe su duale.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-202">In all other cases, avoid setting the class interface to dual.</span></span>

<span data-ttu-id="6c9c0-203">Un'interfaccia duale generata automaticamente può essere appropriata in alcuni casi meno comuni. Nella maggior parte dei casi creerà invece complicazioni in relazione alla gestione delle versioni.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-203">An automatically generated dual interface might be appropriate in rare cases; however, more often it creates version-related complexity.</span></span> <span data-ttu-id="6c9c0-204">Ad esempio, il funzionamento dei client COM che usano l'interfaccia della classe di una classe derivata verrà facilmente compromesso in conseguenza di modifiche della classe base.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-204">For example, COM clients using the class interface of a derived class can easily break with changes to the base class.</span></span> <span data-ttu-id="6c9c0-205">Quando la classe base è fornita da terzi, il layout dell'interfaccia della classe sarà fuori dal proprio controllo.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-205">When a third party provides the base class, the layout of the class interface is out of your control.</span></span> <span data-ttu-id="6c9c0-206">Diversamente da un'interfaccia solo dispatch, un'interfaccia duale (**ClassInterfaceType.AutoDual**) fornisce anche una descrizione dell'interfaccia della classe nella libreria dei tipi esportata.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-206">Further, unlike a dispatch-only interface, a dual interface (**ClassInterfaceType.AutoDual**) provides a description of the class interface in the exported type library.</span></span> <span data-ttu-id="6c9c0-207">Tale descrizione invita i client ad associazione tardiva a memorizzare nella cache i DispId in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-207">Such a description encourages late-bound clients to cache DispIds at compile time.</span></span>

### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a><span data-ttu-id="6c9c0-208">Verificare che tutte le notifiche degli eventi COM siano ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-208">Ensure that all COM event notifications are late-bound.</span></span>

<span data-ttu-id="6c9c0-209">Per impostazione predefinita, le informazioni sui tipi COM sono incorporate direttamente negli assembly gestiti, eliminando così la necessità di assembly di interoperabilità primari.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-209">By default, COM type information is embedded directly into managed assemblies, which eliminates the need for primary interop assemblies (PIAs).</span></span> <span data-ttu-id="6c9c0-210">Tuttavia, uno dei limiti delle informazioni sui tipi incorporate è dato dal fatto che non è supportato il recapito di notifiche di eventi COM tramite chiamate vtable ad associazione anticipata, ma sono supportate solo le chiamate `IDispatch::Invoke` ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="6c9c0-210">However, one of the limitations of embedded type information is that it does not support delivery of COM event notifications by early-bound vtable calls, but only supports late-bound `IDispatch::Invoke` calls.</span></span>

<span data-ttu-id="6c9c0-211">Se l'applicazione richiede chiamate ad associazione anticipata ai metodi dell'interfaccia di eventi COM, è possibile impostare la proprietà **Incorpora tipi di interoperabilità** di Visual Studio su `true` o includere l'elemento seguente nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="6c9c0-211">If your application requires early-bound calls to COM event interface methods, you can set the **Embed Interop Types** property in Visual Studio to `true`, or include the following element in your project file:</span></span>

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a><span data-ttu-id="6c9c0-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c9c0-212">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="6c9c0-213">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="6c9c0-213">COM Wrappers</span></span>](com-wrappers.md)
- [<span data-ttu-id="6c9c0-214">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="6c9c0-214">Exposing .NET Framework Components to COM</span></span>](../../framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="6c9c0-215">Esposizione di componenti .NET Core a COM</span><span class="sxs-lookup"><span data-stu-id="6c9c0-215">Exposing .NET Core Components to COM</span></span>](../../core/native-interop/expose-components-to-com.md)
- [<span data-ttu-id="6c9c0-216">Qualificazione di tipi .NET per l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="6c9c0-216">Qualifying .NET Types for Interoperation</span></span>](qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="6c9c0-217">Runtime Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="6c9c0-217">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
