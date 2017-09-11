---
title: "Cenni preliminari sull'interoperabilità (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c817dcd9073a5a1d4aeee558bf53d50566bbb472
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="30dca-102">Cenni preliminari sull'interoperabilità (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="30dca-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="30dca-103">In questo argomento vengono descritti i metodi per consentire l'interoperabilità tra il codice gestito C# e il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="30dca-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="30dca-104">Platform invoke</span><span class="sxs-lookup"><span data-stu-id="30dca-104">Platform Invoke</span></span>  
 <span data-ttu-id="30dca-105">*Platform invoke* è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in librerie a collegamento dinamico (DLL), come quelle nell'API Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="30dca-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Win32 API.</span></span> <span data-ttu-id="30dca-106">Individua e richiama una funzione esportata ed esegue il marshalling degli argomenti (Integer, stringhe, matrici, strutture e così via) nel limite dell'interazione, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="30dca-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="30dca-107">Per altre informazioni, vedere [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) (Uso di funzioni DLL non gestite) e [Procedura: Usare platform invoke per riprodurre un file audio](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span><span class="sxs-lookup"><span data-stu-id="30dca-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30dca-108">Il [Common Language Runtime](../../../standard/clr.md) (CLR) gestisce l'accesso alle risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="30dca-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="30dca-109">La chiamata di codice non gestito esterno al CLR ignora questo meccanismo di sicurezza e presenta pertanto un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="30dca-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="30dca-110">Ad esempio, il codice non gestito può chiamare direttamente le risorse nel codice non gestito, ignorando i meccanismi di sicurezza CLR.</span><span class="sxs-lookup"><span data-stu-id="30dca-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="30dca-111">Per altre informazioni, vedere [Protezione di .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="30dca-111">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="30dca-112">interoperabilità C++</span><span class="sxs-lookup"><span data-stu-id="30dca-112">C++ Interop</span></span>  
 <span data-ttu-id="30dca-113">È possibile usare l'interoperabilità C++, nota anche come It Just Works (IJW), per eseguire il wrapping di una classe C++ nativa in modo che possa essere usata dal codice creato in C# o in un altro linguaggio .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30dca-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="30dca-114">A tale scopo, scrivere codice C++ per eseguire il wrapping di un componente COM o DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="30dca-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="30dca-115">A differenza degli altri linguaggi .NET Framework, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] offre un supporto all'interoperabilità che consente la presenza di codice gestito e non gestito nella stessa applicazione e perfino nello stesso file.</span><span class="sxs-lookup"><span data-stu-id="30dca-115">Unlike other .NET Framework languages, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="30dca-116">Compilare quindi il codice C++ mediante l'opzione del compilatore **/clr** per produrre un assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="30dca-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="30dca-117">Infine, aggiungere un riferimento all'assembly nel progetto C# e usare gli oggetti con wrapping esattamente come si userebbero altre classi gestite.</span><span class="sxs-lookup"><span data-stu-id="30dca-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="30dca-118">Esposizione di componenti COM a C#</span><span class="sxs-lookup"><span data-stu-id="30dca-118">Exposing COM Components to C#</span></span>  
 <span data-ttu-id="30dca-119">È possibile usare un componente COM da un progetto C#.</span><span class="sxs-lookup"><span data-stu-id="30dca-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="30dca-120">La procedura generale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="30dca-120">The general steps are as follows:</span></span>  
  
1.  <span data-ttu-id="30dca-121">Individuare un componente COM da usare e registrarlo.</span><span class="sxs-lookup"><span data-stu-id="30dca-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="30dca-122">Usare regsvr32.exe per registrare o annullare la registrazione di una DLL COM.</span><span class="sxs-lookup"><span data-stu-id="30dca-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2.  <span data-ttu-id="30dca-123">Aggiungere al progetto un riferimento alla libreria dei componenti o dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="30dca-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="30dca-124">Quando si aggiunge il riferimento [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] usa [Tlbimp.exe (utilità di importazione della libreria dei tipi)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), che accetta una libreria dei tipi come input, per generare un assembly di interoperabilità di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30dca-124">When you add the reference, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses the [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="30dca-125">L'assembly, denominato anche Runtime Callable Wrapper (RCW), contiene le classi gestite e le interfacce che eseguono il wrapping delle classi e interfacce COM presenti nella libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="30dca-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="30dca-126"> aggiunge al progetto un riferimento all'assembly generato.</span><span class="sxs-lookup"><span data-stu-id="30dca-126"> adds to the project a reference to the generated assembly.</span></span>  
  
3.  <span data-ttu-id="30dca-127">Creare un'istanza di una classe definita nell'RCW.</span><span class="sxs-lookup"><span data-stu-id="30dca-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="30dca-128">Essa, a sua volta, crea un'istanza dell'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="30dca-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4.  <span data-ttu-id="30dca-129">Usare l'oggetto allo stesso modo di altri oggetti gestiti.</span><span class="sxs-lookup"><span data-stu-id="30dca-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="30dca-130">Quando l'oggetto viene recuperato da Garbage Collection, anche l'istanza dell'oggetto COM viene rilasciata dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="30dca-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="30dca-131">Per altre informazioni, vedere [Esposizione di componenti COM a .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span><span class="sxs-lookup"><span data-stu-id="30dca-131">For more information, see [Exposing COM Components to the .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="30dca-132">Esposizione di C# a COM</span><span class="sxs-lookup"><span data-stu-id="30dca-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="30dca-133">I client COM possono usare i tipi di C# che sono stati esposti in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="30dca-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="30dca-134">I passaggi di base per esporre tipi di C# sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="30dca-134">The basic steps to expose C# types are as follows:</span></span>  
  
1.  <span data-ttu-id="30dca-135">Aggiungere gli attributi di interoperabilità nel progetto C#.</span><span class="sxs-lookup"><span data-stu-id="30dca-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="30dca-136">È possibile rendere un assembly visibile a COM modificando le proprietà di progetto [!INCLUDE[csprcs](~/includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30dca-136">You can make an assembly COM visible by modifying [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties.</span></span> <span data-ttu-id="30dca-137">Per altre informazioni, vedere [Finestra di dialogo Informazioni assembly](/visualstudio/ide/reference/assembly-information-dialog-box).</span><span class="sxs-lookup"><span data-stu-id="30dca-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2.  <span data-ttu-id="30dca-138">Generare una libreria dei tipi COM e registrarla per l'uso di COM.</span><span class="sxs-lookup"><span data-stu-id="30dca-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="30dca-139">È possibile modificare le proprietà di progetto [!INCLUDE[csprcs](~/includes/csprcs-md.md)] per registrare automaticamente l'assembly C# per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="30dca-139">You can modify [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties to automatically register the C# assembly for COM interop.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="30dca-140"> usa [Regasm.exe (strumento di registrazione di assembly)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), tramite l'opzione della riga di comando `/tlb`, che accetta un assembly gestito come input, per generare una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="30dca-140"> uses the [Regasm.exe (Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="30dca-141">Questa libreria dei tipi descrive i tipi `public` nell'assembly e aggiunge le voci del Registro di sistema in modo che i client COM possano creare classi gestite.</span><span class="sxs-lookup"><span data-stu-id="30dca-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="30dca-142">Per altre informazioni, vedere [Esposizione di componenti .NET Framework a COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) e [Esempio di classe COM](../../../csharp/programming-guide/interop/example-com-class.md).</span><span class="sxs-lookup"><span data-stu-id="30dca-142">For more information, see [Exposing .NET Framework Components to COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) and [Example COM Class](../../../csharp/programming-guide/interop/example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dca-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30dca-143">See Also</span></span>  
 <span data-ttu-id="30dca-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564)  (Miglioramento delle prestazioni di interoperabilità)</span><span class="sxs-lookup"><span data-stu-id="30dca-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564) </span></span>  
 <span data-ttu-id="30dca-145">[Introduzione all'interoperabilità COM](http://go.microsoft.com/fwlink/?LinkId=112406) </span><span class="sxs-lookup"><span data-stu-id="30dca-145">[Introduction to COM Interop](http://go.microsoft.com/fwlink/?LinkId=112406) </span></span>  
 <span data-ttu-id="30dca-146">[Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398)  (Marshalling tra codice gestito e non gestito)</span><span class="sxs-lookup"><span data-stu-id="30dca-146">[Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398) </span></span>  
 <span data-ttu-id="30dca-147">[Interoperabilità con codice non gestito](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="30dca-147">[Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
 <span data-ttu-id="30dca-148">[Interoperabilità COM avanzata](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span><span class="sxs-lookup"><span data-stu-id="30dca-148">[Advanced COM Interoperability](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span></span>  
 [<span data-ttu-id="30dca-149">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="30dca-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

