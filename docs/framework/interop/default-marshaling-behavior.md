---
title: comportamento predefinito del marshalling
description: Informazioni sul comportamento di marshalling predefinito in .NET. Esaminare la gestione della memoria con il marshalling di interoperabilità e vedere Marshalling predefinito per classi, delegati e tipi di valore.
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: 0469874d016725eb6423bb8453e9657b2be923d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618571"
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="74611-104">comportamento predefinito del marshalling</span><span class="sxs-lookup"><span data-stu-id="74611-104">Default Marshaling Behavior</span></span>
<span data-ttu-id="74611-105">Il marshalling di interoperabilità opera sulle regole che stabiliscono il comportamento dei dati associati a parametri del metodo durante il passaggio tra memoria gestita e non gestita.</span><span class="sxs-lookup"><span data-stu-id="74611-105">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="74611-106">Queste regole predefinite controllano tali attività di marshalling come le trasformazioni dei tipi di dati, il fatto che un oggetto chiamato possa modificare i dati passati e restituire tali modifiche al chiamante e le circostanze in cui il gestore di marshalling fornisce ottimizzazioni delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="74611-106">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="74611-107">Questa sezione identifica le caratteristiche predefinite del comportamento del servizio di marshalling di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="74611-107">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="74611-108">Vengono fornite informazioni dettagliate sul marshalling di matrici, tipi booleani, tipi char, delegati, classi, oggetti, stringhe e strutture.</span><span class="sxs-lookup"><span data-stu-id="74611-108">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74611-109">Il marshalling di tipi generici non è supportato.</span><span class="sxs-lookup"><span data-stu-id="74611-109">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="74611-110">Per altre informazioni, vedere [Interoperabilità tramite tipi generici](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="74611-110">For more information see, [Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="74611-111">Gestione della memoria con il marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="74611-111">Memory management with the interop marshaler</span></span>  
 <span data-ttu-id="74611-112">Il gestore di marshalling di interoperabilità tenta sempre di liberare la memoria allocata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-112">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="74611-113">Questo comportamento è conforme alle regole di gestione della memoria COM, ma differisce dalle regole che governano il codice C++ nativo.</span><span class="sxs-lookup"><span data-stu-id="74611-113">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="74611-114">Se si prevede un comportamento C++ nativo (memoria non liberata) quando si usa platform invoke, che libera automaticamente la memoria per i puntatori, può insorgere confusione.</span><span class="sxs-lookup"><span data-stu-id="74611-114">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="74611-115">Ad esempio, se si chiama il metodo non gestito seguente da una DLL C++, non viene liberata automaticamente la memoria.</span><span class="sxs-lookup"><span data-stu-id="74611-115">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="74611-116">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="74611-116">Unmanaged signature</span></span>  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="74611-117">Se, tuttavia, si definisce il metodo come prototipo di platform invoke, si sostituisce ogni tipo **BSTR** con un tipo <xref:System.String> e si chiama `MethodOne`, Common Language Runtime prova a liberare `b` due volte.</span><span class="sxs-lookup"><span data-stu-id="74611-117">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="74611-118">È possibile modificare il comportamento di marshalling usando tipi <xref:System.IntPtr> invece di tipi **String**.</span><span class="sxs-lookup"><span data-stu-id="74611-118">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="74611-119">Il runtime usa sempre il metodo **CoTaskMemFree** per liberare memoria.</span><span class="sxs-lookup"><span data-stu-id="74611-119">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="74611-120">Se la memoria che si sta usando non è stata allocata con il metodo **CoTaskMemAlloc**, è necessario usare un tipo **IntPtr** e liberare la memoria manualmente mediante il metodo appropriato.</span><span class="sxs-lookup"><span data-stu-id="74611-120">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="74611-121">Analogamente, è possibile fare in modo che la memoria non venga liberata automaticamente in situazioni in cui la memoria non deve mai essere liberata, ad esempio quando si usa la funzione **GetCommandLine** da Kernel32.dll, che restituisce un puntatore alla memoria del kernel.</span><span class="sxs-lookup"><span data-stu-id="74611-121">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="74611-122">Per informazioni dettagliate su come liberare manualmente la memoria, vedere [Esempio di buffer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="74611-122">For details on manually freeing memory, see the [Buffers Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="74611-123">Marshalling predefinito per le classi</span><span class="sxs-lookup"><span data-stu-id="74611-123">Default marshaling for classes</span></span>  
 <span data-ttu-id="74611-124">È possibile effettuare il marshalling delle classi solo tramite l'interoperabilità COM e solo come interfacce.</span><span class="sxs-lookup"><span data-stu-id="74611-124">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="74611-125">In alcuni casi l'interfaccia usata per il marshalling della classe è nota come interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="74611-125">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="74611-126">Per informazioni sull'override dell'interfaccia di classe con un'interfaccia di propria scelta, vedere [Introduzione all'interfaccia della classe](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="74611-126">For information about overriding the class interface with an interface of your choice, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="74611-127">Passaggio di classi a COM</span><span class="sxs-lookup"><span data-stu-id="74611-127">Passing Classes to COM</span></span>  
 <span data-ttu-id="74611-128">Quando una classe gestita viene passata a COM, il marshalling di interoperabilità esegue automaticamente il wrapping della classe con un proxy COM e passa l'interfaccia di classe creata dal proxy alla chiamata al metodo COM.</span><span class="sxs-lookup"><span data-stu-id="74611-128">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="74611-129">Il proxy delega quindi tutte le chiamate sull'interfaccia di classe all'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-129">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="74611-130">Il proxy espone anche altre interfacce non implementate in modo esplicito dalla classe.</span><span class="sxs-lookup"><span data-stu-id="74611-130">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="74611-131">Il proxy implementa automaticamente interfacce come **IUnknown** e **IDispatch** per conto della classe.</span><span class="sxs-lookup"><span data-stu-id="74611-131">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="74611-132">Passaggio di classi al codice .NET</span><span class="sxs-lookup"><span data-stu-id="74611-132">Passing Classes to .NET Code</span></span>  
 <span data-ttu-id="74611-133">Le coclassi non sono in genere usate come argomenti dei metodi in COM.</span><span class="sxs-lookup"><span data-stu-id="74611-133">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="74611-134">Al posto della coclasse viene invece in genere passata un'interfaccia predefinita.</span><span class="sxs-lookup"><span data-stu-id="74611-134">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="74611-135">Quando viene passata un'interfaccia nel codice gestito, il gestore di marshalling di interoperabilità è responsabile di effettuare il wrapping dell'interfaccia con il wrapper appropriato e di passare il wrapper al metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-135">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="74611-136">La determinazione del wrapper da usare può essere complessa.</span><span class="sxs-lookup"><span data-stu-id="74611-136">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="74611-137">Ogni istanza di un oggetto COM prevede un singolo wrapper univoco, indipendentemente dal numero di interfacce implementate dall'oggetto.</span><span class="sxs-lookup"><span data-stu-id="74611-137">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="74611-138">Ad esempio, un singolo oggetto COM che implementa cinque interfacce distinte ha solo un wrapper.</span><span class="sxs-lookup"><span data-stu-id="74611-138">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="74611-139">Lo stesso wrapper espone tutte e cinque le interfacce.</span><span class="sxs-lookup"><span data-stu-id="74611-139">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="74611-140">Se vengono create due istanze dell'oggetto COM, vengono create due istanze del wrapper.</span><span class="sxs-lookup"><span data-stu-id="74611-140">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="74611-141">Affinché il wrapper mantenga lo stesso tipo per tutta la sua durata, il gestore di marshalling di interoperabilità deve identificare il wrapper corretto la prima volta che un'interfaccia esposta dall'oggetto viene passata attraverso di esso.</span><span class="sxs-lookup"><span data-stu-id="74611-141">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="74611-142">Il gestore di marshalling identifica l'oggetto analizzando una delle interfacce implementate.</span><span class="sxs-lookup"><span data-stu-id="74611-142">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="74611-143">Ad esempio, il gestore di marshalling determina che il wrapper della classe deve essere usato per eseguire il wrapping dell'interfaccia passata al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-143">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="74611-144">Quando l'interfaccia viene passata per la prima volta attraverso il gestore di marshalling, quest'ultimo controlla se l'interfaccia proviene da un oggetto noto.</span><span class="sxs-lookup"><span data-stu-id="74611-144">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="74611-145">Questo controllo viene eseguito in due situazioni:</span><span class="sxs-lookup"><span data-stu-id="74611-145">This check occurs in two situations:</span></span>  
  
- <span data-ttu-id="74611-146">Quando un'interfaccia viene implementata da un altro oggetto gestito passato a COM in un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="74611-146">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="74611-147">Il gestore di marshalling può identificare immediatamente le interfacce esposte dagli oggetti gestiti ed è in grado di associare l'interfaccia all'oggetto gestito che fornisce l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="74611-147">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="74611-148">L'oggetto gestito viene quindi passato al metodo e non sono necessari wrapper.</span><span class="sxs-lookup"><span data-stu-id="74611-148">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
- <span data-ttu-id="74611-149">Quando un oggetto di cui è già stato eseguito il wrapping implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="74611-149">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="74611-150">Per determinare se questo è il caso, il gestore di marshalling invia una query all'oggetto per l'interfaccia **IUnknown** e confronta l'interfaccia restituita con le interfacce di altri oggetti di cui è già stato eseguito il wrapping.</span><span class="sxs-lookup"><span data-stu-id="74611-150">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="74611-151">Se l'interfaccia corrisponde a quella di un altro wrapper, gli oggetti hanno la stessa identità e il wrapper esistente viene passato al metodo.</span><span class="sxs-lookup"><span data-stu-id="74611-151">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="74611-152">Se un'interfaccia non proviene da un oggetto noto, il gestore di marshalling esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74611-152">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1. <span data-ttu-id="74611-153">Il gestore di marshalling invia una query all'oggetto per l'interfaccia **IProvideClassInfo2**.</span><span class="sxs-lookup"><span data-stu-id="74611-153">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="74611-154">Se specificato, il gestore di marshalling usa il CLSID restituito da **IProvideClassInfo2.GetGUID** per identificare la coclasse che fornisce l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="74611-154">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="74611-155">Con il CLSID, il gestore di marshalling può individuare il wrapper dal Registro di sistema se l'assembly è stato registrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74611-155">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2. <span data-ttu-id="74611-156">Il gestore di marshalling invia una query all'interfaccia per l'interfaccia **IProvideClassInfo**.</span><span class="sxs-lookup"><span data-stu-id="74611-156">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="74611-157">Se specificato, il gestore di marshalling usa l'oggetto **ITypeInfo** restituito da **IProvideClassInfo.GetClassinfo** per determinare il CLSID della classe che espone l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="74611-157">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="74611-158">Il gestore di marshalling può usare il CLSID per individuare i metadati per il wrapper.</span><span class="sxs-lookup"><span data-stu-id="74611-158">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3. <span data-ttu-id="74611-159">Se il gestore di marshalling non riesce ancora a identificare la classe, esegue il wrapping dell'interfaccia con una classe wrapper generica denominata **System.__ComObject**.</span><span class="sxs-lookup"><span data-stu-id="74611-159">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="74611-160">Marshalling predefinito per i delegati</span><span class="sxs-lookup"><span data-stu-id="74611-160">Default marshaling for delegates</span></span>  
 <span data-ttu-id="74611-161">Un delegato gestito viene sottoposto a marshalling come un'interfaccia COM o come un puntatore a funzione, in base al meccanismo di chiamata:</span><span class="sxs-lookup"><span data-stu-id="74611-161">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
- <span data-ttu-id="74611-162">Per platform invoke, un delegato viene sottoposto a marshalling come puntatore a funzione non gestito per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="74611-162">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
- <span data-ttu-id="74611-163">Per l'interoperabilità COM, un delegato viene sottoposto a marshalling come interfaccia COM di tipo **_Delegate** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="74611-163">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="74611-164">L'interfaccia **_Delegate** è definita nella libreria dei tipi Mscorlib.tlb e contiene il metodo <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>, che consente di chiamare il metodo a cui fa riferimento il delegato.</span><span class="sxs-lookup"><span data-stu-id="74611-164">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="74611-165">La tabella seguente illustra le opzioni di marshalling per il tipo di dati delegato gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-165">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="74611-166">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce diversi valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di delegati.</span><span class="sxs-lookup"><span data-stu-id="74611-166">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="74611-167">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="74611-167">Enumeration type</span></span>|<span data-ttu-id="74611-168">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="74611-168">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="74611-169">**UnmanagedType.FunctionPtr**</span><span class="sxs-lookup"><span data-stu-id="74611-169">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="74611-170">Puntatore alla funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="74611-170">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="74611-171">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="74611-171">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="74611-172">Interfaccia di tipo **_Delegate**, definita in Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="74611-172">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="74611-173">Si consideri l'esempio di codice seguente in cui i metodi di `DelegateTestInterface` vengono esportati in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="74611-173">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="74611-174">Si noti che solo i delegati contrassegnati con la parola chiave **ref** (o **ByRef**) vengono passati come parametri in/out.</span><span class="sxs-lookup"><span data-stu-id="74611-174">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);
}  
```  
  
### <a name="type-library-representation"></a><span data-ttu-id="74611-175">Rappresentazione di libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="74611-175">Type library representation</span></span>  
  
```cpp  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 <span data-ttu-id="74611-176">È possibile dereferenziare un puntatore a funzione, così come qualsiasi altro puntatore a funzione non gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-176">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  

<span data-ttu-id="74611-177">In questo esempio, quando i due delegati sono sottoposti a marshalling come <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, il risultato è un `int` e un puntatore a un `int`.</span><span class="sxs-lookup"><span data-stu-id="74611-177">In this example, when the two delegates are marshaled as <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, the result is an `int` and a pointer to an `int`.</span></span> <span data-ttu-id="74611-178">Dal momento che i tipi delegati sono sottoposti a marshalling, `int` in questo caso rappresenta un puntatore a un void (`void*`), ovvero l'indirizzo del delegato in memoria.</span><span class="sxs-lookup"><span data-stu-id="74611-178">Because delegate types are being marshaled, `int` here represents a pointer to a void (`void*`), which is the address of the delegate in memory.</span></span> <span data-ttu-id="74611-179">In altre parole, questo risultato è specifico per i sistemi Windows a 32 bit, poiché `int` in questo caso rappresenta la dimensione del puntatore a funzione.</span><span class="sxs-lookup"><span data-stu-id="74611-179">In other words, this result is specific to 32-bit Windows systems, since `int` here represents the size of the function pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="74611-180">Un riferimento al puntatore a funzione a un delegato gestito tramite codice non gestito non impedisce a Common Language Runtime di eseguire un'operazione di Garbage Collection nell'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-180">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="74611-181">Il codice seguente, ad esempio, non è corretto perché il riferimento all'oggetto `cb`, passato al metodo  `SetChangeHandler` non mantiene attivo `cb` oltre la durata del metodo `Test`.</span><span class="sxs-lookup"><span data-stu-id="74611-181">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="74611-182">Dopo che l'oggetto `cb` è stato sottoposto a Garbage Collection, il puntatore a funzione passato a `SetChangeHandler` non è più valido.</span><span class="sxs-lookup"><span data-stu-id="74611-182">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the
      // object from being garbage collected after the Main method
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));
   }  
}  
```  
  
 <span data-ttu-id="74611-183">Per compensare un'operazione di Garbage Collection non prevista, il chiamante deve fare in modo che l'oggetto `cb` venga mantenuto attivo fino a quando il puntatore a funzione non gestito è in uso.</span><span class="sxs-lookup"><span data-stu-id="74611-183">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="74611-184">Facoltativamente, è possibile fare in modo che il codice non gestito segnali al codice gestito quando il puntatore a funzione non è più necessario, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="74611-184">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="74611-185">Marshalling predefinito per i tipi di valore</span><span class="sxs-lookup"><span data-stu-id="74611-185">Default marshaling for value types</span></span>  
 <span data-ttu-id="74611-186">La maggior parte dei tipi valore, ad esempio numeri a virgola mobile e interi, è [copiabile da BLT](blittable-and-non-blittable-types.md) e non richiede di effettuare il marshalling.</span><span class="sxs-lookup"><span data-stu-id="74611-186">Most value types, such as integers and floating-point numbers, are [blittable](blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="74611-187">Altri tipi [non copiabili da BLT](blittable-and-non-blittable-types.md) hanno rappresentazioni diverse nella memoria gestita e non gestita e richiedono il marshalling.</span><span class="sxs-lookup"><span data-stu-id="74611-187">Other [non-blittable](blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="74611-188">Altri tipi ancora richiedono la formattazione esplicita oltre i limiti di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="74611-188">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="74611-189">Questa sezione contiene informazioni sui tipi di valore formattati seguenti:</span><span class="sxs-lookup"><span data-stu-id="74611-189">This section provides information on the following formatted value types:</span></span>  
  
- [<span data-ttu-id="74611-190">Tipi di valore usati in platform invoke</span><span class="sxs-lookup"><span data-stu-id="74611-190">Value Types Used in Platform Invoke</span></span>](#value-types-used-in-platform-invoke)  
  
- [<span data-ttu-id="74611-191">Tipi di valore usati nell'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="74611-191">Value Types Used in COM Interop</span></span>](#value-types-used-in-com-interop)  
  
 <span data-ttu-id="74611-192">Oltre a descrivere i tipi formattati, questo argomento identifica i [tipi valore di sistema](#system-value-types) che presentano un comportamento di marshalling insolito.</span><span class="sxs-lookup"><span data-stu-id="74611-192">In addition to describing formatted types, this topic identifies [System Value Types](#system-value-types) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="74611-193">Un tipo formattato è un tipo complesso che contiene informazioni che controllano in modo esplicito il layout dei relativi membri in memoria.</span><span class="sxs-lookup"><span data-stu-id="74611-193">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="74611-194">Le informazioni sul layout dei membri vengono fornite tramite l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="74611-194">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="74611-195">Il layout può essere uno dei seguenti valori di enumerazione <xref:System.Runtime.InteropServices.LayoutKind>:</span><span class="sxs-lookup"><span data-stu-id="74611-195">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
- <span data-ttu-id="74611-196">**LayoutKind. auto**</span><span class="sxs-lookup"><span data-stu-id="74611-196">**LayoutKind.Auto**</span></span>  
  
     <span data-ttu-id="74611-197">Indica che Common Language Runtime può riordinare i membri del tipo per migliorare l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="74611-197">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="74611-198">Tuttavia, quando un tipo di valore viene passato al codice non gestito, il layout dei membri è prevedibile.</span><span class="sxs-lookup"><span data-stu-id="74611-198">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="74611-199">Un tentativo di effettuare automaticamente il marshalling di tale struttura provoca un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="74611-199">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
- <span data-ttu-id="74611-200">**LayoutKind.Sequential**</span><span class="sxs-lookup"><span data-stu-id="74611-200">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="74611-201">Indica che i membri del tipo devono essere disposti nella memoria non gestita nello stesso ordine in cui appaiono nella definizione del tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-201">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
- <span data-ttu-id="74611-202">**LayoutKind.Explicit**</span><span class="sxs-lookup"><span data-stu-id="74611-202">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="74611-203">Indica che i membri vengono disposti in base all'oggetto <xref:System.Runtime.InteropServices.FieldOffsetAttribute> fornito con ogni campo.</span><span class="sxs-lookup"><span data-stu-id="74611-203">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="74611-204">Tipi di valore usati in platform invoke</span><span class="sxs-lookup"><span data-stu-id="74611-204">Value Types Used in Platform Invoke</span></span>  
 <span data-ttu-id="74611-205">Nell'esempio seguente i tipi `Point` e `Rect` forniscono informazioni sul layout dei membri usando **StructLayoutAttribute**.</span><span class="sxs-lookup"><span data-stu-id="74611-205">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
   public int x;  
   public int y;  
}
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
   [FieldOffset(0)] public int left;  
   [FieldOffset(4)] public int top;  
   [FieldOffset(8)] public int right;  
   [FieldOffset(12)] public int bottom;  
}  
```  
  
 <span data-ttu-id="74611-206">Quando si effettua il marshalling nel codice non gestito, questi tipi formattati vengono sottoposti a marshalling come strutture di tipo C.</span><span class="sxs-lookup"><span data-stu-id="74611-206">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="74611-207">Ciò consente di chiamare in modo semplice un'API non gestita con argomenti di struttura.</span><span class="sxs-lookup"><span data-stu-id="74611-207">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="74611-208">Ad esempio, le strutture `POINT` e `RECT` possono essere passate alla funzione **PtInRect** dell'API Microsoft Windows come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="74611-208">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Windows API **PtInRect** function as follows:</span></span>  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="74611-209">È possibile passare le strutture usando la definizione di platform invoke seguente:</span><span class="sxs-lookup"><span data-stu-id="74611-209">You can pass structures using the following platform invoke definition:</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "User32.dll" (
        ByRef r As Rect, p As Point) As Boolean
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("User32.dll")]
   internal static extern bool PtInRect(ref Rect r, Point p);
}
```
  
 <span data-ttu-id="74611-210">Il tipo di valore `Rect` deve essere passato mediante riferimento in quanto l'API non gestita richiede che alla funzione venga passato un puntatore a un oggetto `RECT`.</span><span class="sxs-lookup"><span data-stu-id="74611-210">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="74611-211">Il tipo di valore `Point` viene passato mediante valore in quanto l'API non gestita richiede che nello stack venga passato un oggetto `POINT`.</span><span class="sxs-lookup"><span data-stu-id="74611-211">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="74611-212">Questa sottile differenza è molto importante.</span><span class="sxs-lookup"><span data-stu-id="74611-212">This subtle difference is very important.</span></span> <span data-ttu-id="74611-213">I riferimenti vengono passati al codice non gestito come puntatori.</span><span class="sxs-lookup"><span data-stu-id="74611-213">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="74611-214">I valori vengono passati al codice non gestito nello stack.</span><span class="sxs-lookup"><span data-stu-id="74611-214">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74611-215">Quando viene effettuato il marshalling di un tipo formattato come struttura, solo i campi all'interno del tipo sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="74611-215">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="74611-216">Se il tipo dispone di metodi, proprietà o eventi, non è possibile accedervi dal codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-216">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="74611-217">È anche possibile effettuare il marshalling delle classi nel codice non gestito come strutture di tipo C, a condizione che il layout dei membri sia fisso.</span><span class="sxs-lookup"><span data-stu-id="74611-217">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="74611-218">Le informazioni sul layout dei membri per una classe vengono fornite anche tramite l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="74611-218">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="74611-219">La differenza principale tra i tipi di valore con layout fisso e le classi con layout fisso riguarda il modo in cui viene effettuato il marshalling nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="74611-219">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="74611-220">I tipi di valore vengono passati mediante valore (nello stack) e, di conseguenza, le eventuali modifiche apportate ai membri del tipo dall'oggetto chiamato non sono visibili al chiamante.</span><span class="sxs-lookup"><span data-stu-id="74611-220">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="74611-221">I tipi di riferimento vengono passati mediante riferimento (un riferimento al tipo viene passato nello stack) e, di conseguenza, tutte le modifiche apportate ai membri di un tipo copiabile da BLT dall'oggetto chiamato sono visibili al chiamante.</span><span class="sxs-lookup"><span data-stu-id="74611-221">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74611-222">Se un tipo di riferimento dispone di membri di tipi non copiabili da BLT, è necessario eseguire la conversione due volte: la prima volta quando un argomento viene passato al lato non gestito e la seconda volta quando viene restituito dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="74611-222">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="74611-223">A causa di questo sovraccarico aggiuntivo, è necessario applicare in modo esplicito i parametri in/out a un argomento se il chiamante desidera visualizzare le modifiche apportate dall'oggetto chiamato.</span><span class="sxs-lookup"><span data-stu-id="74611-223">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="74611-224">Nell'esempio seguente la classe `SystemTime` ha un layout dei membri sequenziale e può essere passata alla funzione **GetSystemTime** dell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="74611-224">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Windows API **GetSystemTime** function.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;
   public ushort wMonth;  
   public ushort wDayOfWeek;
   public ushort wDay;
   public ushort wHour;
   public ushort wMinute;
   public ushort wSecond;
   public ushort wMilliseconds;
}  
```  
  
 <span data-ttu-id="74611-225">La funzione **GetSystemTime** è definita come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="74611-225">The **GetSystemTime** function is defined as follows:</span></span>  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="74611-226">La definizione di platform invoke equivalente per **GetSystemTime** è la seguente:</span><span class="sxs-lookup"><span data-stu-id="74611-226">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        ByVal sysTime As SystemTime)
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("Kernel32.dll", CharSet = CharSet.Auto)]
   internal static extern void GetSystemTime(SystemTime st);
}
```
  
 <span data-ttu-id="74611-227">Si noti che l'argomento `SystemTime` non è tipizzato come argomento di riferimento poiché `SystemTime` è una classe e non un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="74611-227">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="74611-228">A differenza dei tipi di valore, le classi vengono sempre passate mediante riferimento.</span><span class="sxs-lookup"><span data-stu-id="74611-228">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="74611-229">L'esempio di codice seguente mostra una classe `Point` diversa con un metodo denominato `SetXY`.</span><span class="sxs-lookup"><span data-stu-id="74611-229">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="74611-230">Poiché il tipo ha un layout sequenziale, può essere passato al codice non gestito e sottoposto a marshalling come una struttura.</span><span class="sxs-lookup"><span data-stu-id="74611-230">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="74611-231">Tuttavia, il membro `SetXY` non può essere chiamato dal codice non gestito, anche se l'oggetto viene passato mediante riferimento.</span><span class="sxs-lookup"><span data-stu-id="74611-231">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="74611-232">Tipi di valore usati nell'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="74611-232">Value Types Used in COM Interop</span></span>  
 <span data-ttu-id="74611-233">I tipi formattati possono anche essere passati alle chiamate ai metodi di interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="74611-233">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="74611-234">Quando vengono esportati in una libreria dei tipi, infatti, i tipi di valore vengono convertiti automaticamente in strutture.</span><span class="sxs-lookup"><span data-stu-id="74611-234">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="74611-235">Come illustrato nell'esempio seguente, il tipo di valore `Point` diventa una definizione di tipo (typedef) con il nome `Point`.</span><span class="sxs-lookup"><span data-stu-id="74611-235">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="74611-236">Tutti i riferimenti al tipo di valore `Point` in altre posizioni nella libreria dei tipi vengono sostituiti con la definizione di tipo `Point`.</span><span class="sxs-lookup"><span data-stu-id="74611-236">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="74611-237">**Rappresentazione della libreria di tipi**</span><span class="sxs-lookup"><span data-stu-id="74611-237">**Type library representation**</span></span>  
  
```cpp  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 <span data-ttu-id="74611-238">Le stesse regole usate per il marshalling di valori e riferimenti nelle chiamate di platform invoke vengono usate per il marshalling tramite le interfacce COM.</span><span class="sxs-lookup"><span data-stu-id="74611-238">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="74611-239">Ad esempio, quando un'istanza del tipo di valore `Point` viene passata da .NET Framework a COM, `Point` viene passato mediante valore.</span><span class="sxs-lookup"><span data-stu-id="74611-239">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="74611-240">Se il tipo di valore `Point` viene passato mediante riferimento, viene passato un puntatore a un oggetto `Point` nello stack.</span><span class="sxs-lookup"><span data-stu-id="74611-240">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="74611-241">Il gestore marshalling di interoperabilità non supporta livelli superiori di riferimento indiretto (**Point** \*\*) in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="74611-241">The interop marshaler does not support higher levels of indirection (**Point** \*\*) in either direction.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74611-242">Le strutture con valore di enumerazione <xref:System.Runtime.InteropServices.LayoutKind> impostato su **Explicit** non possono essere usate nell'interoperabilità COM perché la libreria dei tipi esportata non può esprimere un layout esplicito.</span><span class="sxs-lookup"><span data-stu-id="74611-242">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
### <a name="system-value-types"></a><span data-ttu-id="74611-243">Tipi di valore di sistema</span><span class="sxs-lookup"><span data-stu-id="74611-243">System Value Types</span></span>  
 <span data-ttu-id="74611-244">Lo spazio dei nomi <xref:System> include diversi tipi di valore che rappresentano il formato sottoposto a conversione boxing dei tipi primitivi di runtime.</span><span class="sxs-lookup"><span data-stu-id="74611-244">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="74611-245">Ad esempio, la struttura <xref:System.Int32?displayProperty=nameWithType> del tipo valore rappresenta il formato sottoposto a conversione boxing di **ELEMENT_TYPE_I4**.</span><span class="sxs-lookup"><span data-stu-id="74611-245">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="74611-246">Anziché effettuare il marshalling di questi tipi come strutture, come nel caso di altri tipi formattati, si effettua il marshalling nello stesso modo dei tipi primitivi di cui viene eseguita la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="74611-246">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="74611-247">Per **System.Int32** viene quindi effettuato il marshalling come **ELEMENT_TYPE_I4** invece che come struttura contenente un singolo membro di tipo **long**.</span><span class="sxs-lookup"><span data-stu-id="74611-247">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="74611-248">La tabella seguente contiene un elenco dei tipi valore nello spazio dei nomi **System** che costituiscono rappresentazioni sottoposte a conversione boxing di tipi primitivi.</span><span class="sxs-lookup"><span data-stu-id="74611-248">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="74611-249">Tipo di valore di sistema</span><span class="sxs-lookup"><span data-stu-id="74611-249">System value type</span></span>|<span data-ttu-id="74611-250">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="74611-250">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="74611-251">**ELEMENT_TYPE_BOOLEAN**</span><span class="sxs-lookup"><span data-stu-id="74611-251">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="74611-252">**ELEMENT_TYPE_I1**</span><span class="sxs-lookup"><span data-stu-id="74611-252">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="74611-253">**ELEMENT_TYPE_UI1**</span><span class="sxs-lookup"><span data-stu-id="74611-253">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="74611-254">**ELEMENT_TYPE_CHAR**</span><span class="sxs-lookup"><span data-stu-id="74611-254">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="74611-255">**ELEMENT_TYPE_I2**</span><span class="sxs-lookup"><span data-stu-id="74611-255">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="74611-256">**ELEMENT_TYPE_U2**</span><span class="sxs-lookup"><span data-stu-id="74611-256">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="74611-257">**ELEMENT_TYPE_I4**</span><span class="sxs-lookup"><span data-stu-id="74611-257">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="74611-258">**ELEMENT_TYPE_U4**</span><span class="sxs-lookup"><span data-stu-id="74611-258">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="74611-259">**ELEMENT_TYPE_I8**</span><span class="sxs-lookup"><span data-stu-id="74611-259">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="74611-260">**ELEMENT_TYPE_U8**</span><span class="sxs-lookup"><span data-stu-id="74611-260">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="74611-261">**ELEMENT_TYPE_R4**</span><span class="sxs-lookup"><span data-stu-id="74611-261">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="74611-262">**ELEMENT_TYPE_R8**</span><span class="sxs-lookup"><span data-stu-id="74611-262">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="74611-263">**ELEMENT_TYPE_STRING**</span><span class="sxs-lookup"><span data-stu-id="74611-263">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="74611-264">**ELEMENT_TYPE_I**</span><span class="sxs-lookup"><span data-stu-id="74611-264">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="74611-265">**ELEMENT_TYPE_U**</span><span class="sxs-lookup"><span data-stu-id="74611-265">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="74611-266">Alcuni altri tipi valore nello spazio dei nomi **System** vengono gestiti diversamente.</span><span class="sxs-lookup"><span data-stu-id="74611-266">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="74611-267">Poiché il codice non gestito dispone già di formati ben definiti per questi tipi, il gestore di marshalling ha regole speciali per il loro marshalling.</span><span class="sxs-lookup"><span data-stu-id="74611-267">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="74611-268">La tabella seguente elenca i tipi valore speciali nello spazio dei nomi **System**, nonché il tipo non gestito a cui viene effettuato il marshalling.</span><span class="sxs-lookup"><span data-stu-id="74611-268">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="74611-269">Tipo di valore di sistema</span><span class="sxs-lookup"><span data-stu-id="74611-269">System value type</span></span>|<span data-ttu-id="74611-270">Tipo IDL</span><span class="sxs-lookup"><span data-stu-id="74611-270">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="74611-271">**Data**</span><span class="sxs-lookup"><span data-stu-id="74611-271">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="74611-272">**DECIMALE**</span><span class="sxs-lookup"><span data-stu-id="74611-272">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="74611-273">**GUID**</span><span class="sxs-lookup"><span data-stu-id="74611-273">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="74611-274">**OLE_COLOR**</span><span class="sxs-lookup"><span data-stu-id="74611-274">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="74611-275">Il codice seguente mostra la definizione dei tipi non gestiti **DATE**, **GUID**, **DECIMAL** e **OLE_COLOR** nella libreria dei tipi Stdole2.</span><span class="sxs-lookup"><span data-stu-id="74611-275">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="74611-276">Rappresentazione di libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="74611-276">Type library representation</span></span>  
  
```cpp  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 <span data-ttu-id="74611-277">Il codice seguente mostra le definizioni corrispondenti nell'interfaccia `IValueTypes` gestita.</span><span class="sxs-lookup"><span data-stu-id="74611-277">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a><span data-ttu-id="74611-278">Rappresentazione di libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="74611-278">Type library representation</span></span>  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="74611-279">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74611-279">See also</span></span>

- [<span data-ttu-id="74611-280">tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="74611-280">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- [<span data-ttu-id="74611-281">copia e blocco</span><span class="sxs-lookup"><span data-stu-id="74611-281">Copying and Pinning</span></span>](copying-and-pinning.md)
- [<span data-ttu-id="74611-282">Marshalling predefinito per le matrici</span><span class="sxs-lookup"><span data-stu-id="74611-282">Default Marshaling for Arrays</span></span>](default-marshaling-for-arrays.md)
- [<span data-ttu-id="74611-283">Marshalling predefinito per gli oggetti</span><span class="sxs-lookup"><span data-stu-id="74611-283">Default Marshaling for Objects</span></span>](default-marshaling-for-objects.md)
- [<span data-ttu-id="74611-284">Marshalling predefinito per le stringhe</span><span class="sxs-lookup"><span data-stu-id="74611-284">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
