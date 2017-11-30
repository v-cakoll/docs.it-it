---
title: 'Procedura: creare wrapper manualmente'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19f605203a79f8435d414fb3c2eb7041c9824640
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="cd199-102">Procedura: creare wrapper manualmente</span><span class="sxs-lookup"><span data-stu-id="cd199-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="cd199-103">Se si decide di dichiarare manualmente i tipi COM nel codice sorgente gestito, è consigliabile iniziare con una libreria dei tipi o un file IDL esistente.</span><span class="sxs-lookup"><span data-stu-id="cd199-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="cd199-104">Se non si ha il file IDL o non è possibile generare un file di libreria dei tipi, simulare i tipi COM mediante la creazione di dichiarazioni gestite e l'esportazione dell'assembly risultante in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="cd199-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="cd199-105">Per simulare i tipi COM dall'origine gestita</span><span class="sxs-lookup"><span data-stu-id="cd199-105">To simulate COM types from managed source</span></span>  
  
1.  <span data-ttu-id="cd199-106">Dichiarare i tipi in un linguaggio conformi a Common Language Specification (CLS) e compilare il file.</span><span class="sxs-lookup"><span data-stu-id="cd199-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2.  <span data-ttu-id="cd199-107">Esportare l'assembly contenente i tipi con l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="cd199-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3.  <span data-ttu-id="cd199-108">Usare la libreria dei tipi COM esportata come base per la dichiarazione dei tipi gestiti orientati a COM.</span><span class="sxs-lookup"><span data-stu-id="cd199-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="cd199-109">Per creare un Runtime Callable Wrapper (RCW)</span><span class="sxs-lookup"><span data-stu-id="cd199-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1.  <span data-ttu-id="cd199-110">Se si dispone di un file IDL o di un file di libreria dei tipi, decidere quali classi e interfacce includere nell'RCW personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cd199-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="cd199-111">È possibile escludere i tipi che non si intende usare direttamente o indirettamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cd199-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2.  <span data-ttu-id="cd199-112">Creare un file di origine in un linguaggio conforme a Common Language Specification e dichiarare i tipi.</span><span class="sxs-lookup"><span data-stu-id="cd199-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="cd199-113">Per una descrizione completa del processo di conversione dell'importazione, vedere [Riepilogo della conversione della libreria dei tipi in assembly](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958).</span><span class="sxs-lookup"><span data-stu-id="cd199-113">See [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958) for a complete description of the import conversion process.</span></span> <span data-ttu-id="cd199-114">In pratica, quando si crea un RCW personalizzato si esegue manualmente la conversione dei tipi fornita dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="cd199-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="cd199-115">Nell'esempio riportato nella sezione seguente vengono illustrati i tipi di un file della libreria dei tipi o IDL e i tipi corrispondenti nel codice C#.</span><span class="sxs-lookup"><span data-stu-id="cd199-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3.  <span data-ttu-id="cd199-116">Dopo aver completato le dichiarazioni, compilare il file come si compila qualunque altro codice sorgente gestito.</span><span class="sxs-lookup"><span data-stu-id="cd199-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4.  <span data-ttu-id="cd199-117">Come per i tipi importati con Tlbimp.exe, alcuni tipi richiedono altre informazioni che è possibile aggiungere direttamente al codice.</span><span class="sxs-lookup"><span data-stu-id="cd199-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="cd199-118">Per dettagli, vedere [Procedura: Modificare assembly di interoperabilità](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277).</span><span class="sxs-lookup"><span data-stu-id="cd199-118">For details, see [How to: Edit Interop Assemblies](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd199-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd199-119">Example</span></span>  
 <span data-ttu-id="cd199-120">Il codice seguente mostra un esempio di interfaccia `ISATest` e di classe `SATest` in IDL e i tipi corrispondenti nel codice sorgente C#.</span><span class="sxs-lookup"><span data-stu-id="cd199-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="cd199-121">**IDL o file di libreria dei tipi**</span><span class="sxs-lookup"><span data-stu-id="cd199-121">**IDL or type library file**</span></span>  
  
```  
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="cd199-122">**Wrapper nel codice sorgente gestito**</span><span class="sxs-lookup"><span data-stu-id="cd199-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd199-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd199-123">See Also</span></span>  
 [<span data-ttu-id="cd199-124">Personalizzazione dei Runtime Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="cd199-124">Customizing Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 [<span data-ttu-id="cd199-125">Tipi di dati COM</span><span class="sxs-lookup"><span data-stu-id="cd199-125">COM Data Types</span></span>](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 [<span data-ttu-id="cd199-126">Procedura: modificare assembly di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd199-126">How to: Edit Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277)  
 [<span data-ttu-id="cd199-127">Riepilogo della conversione da libreria dei tipi ad assembly</span><span class="sxs-lookup"><span data-stu-id="cd199-127">Type Library to Assembly Conversion Summary</span></span>](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 [<span data-ttu-id="cd199-128">Tlbimp.exe (utilità di importazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="cd199-128">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="cd199-129">Tlbexp.exe (utilità di esportazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="cd199-129">Tlbexp.exe (Type Library Exporter)</span></span>](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)
