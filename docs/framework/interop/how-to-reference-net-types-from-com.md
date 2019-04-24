---
title: 'Procedura: Fare riferimento a tipi .NET da COM'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e033ba4b3b98367452b355363058adc7f1a5887
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198400"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="e92fd-102">Procedura: Fare riferimento a tipi .NET da COM</span><span class="sxs-lookup"><span data-stu-id="e92fd-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="e92fd-103">Dal punto di vista del codice client e server, le differenze tra COM e .NET Framework sono in gran parte invisibili.</span><span class="sxs-lookup"><span data-stu-id="e92fd-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="e92fd-104">I client di Microsoft Visual Basic possono visualizzare un oggetto .NET nel Visualizzatore oggetti, che espone i metodi e la sintassi, le proprietà e i campi dell'oggetto esattamente come se si trattasse di un normale oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="e92fd-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="e92fd-105">Il processo per l'importazione di una libreria dei tipi è leggermente più complesso per i client C++, anche se si usano gli stessi strumenti per esportare i metadati in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="e92fd-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="e92fd-106">Per fare riferimento a membri di oggetti .NET da un client C++ non gestito, fare riferimento al file TLB (prodotto con Tlbexp.exe) con la direttiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="e92fd-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="e92fd-107">Quando si fa riferimento a una libreria dei tipi da C++, è necessario specificare l'opzione **raw_interfaces_only** o importare le definizioni nella libreria di classi di base, Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="e92fd-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="e92fd-108">Per importare una libreria</span><span class="sxs-lookup"><span data-stu-id="e92fd-108">To import a library</span></span>  
  
-   <span data-ttu-id="e92fd-109">Specificare l'opzione **raw_interfaces_only** nella direttiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="e92fd-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="e92fd-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e92fd-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="e92fd-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e92fd-111">-or-</span></span>  
  
-   <span data-ttu-id="e92fd-112">Includere una direttiva #import per Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="e92fd-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="e92fd-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e92fd-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e92fd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e92fd-114">See also</span></span>

- [<span data-ttu-id="e92fd-115">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="e92fd-115">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="e92fd-116">Registrazione di assembly presso COM</span><span class="sxs-lookup"><span data-stu-id="e92fd-116">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="e92fd-117">[Chiamata di un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e92fd-117">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="e92fd-118">[Distribuzione di un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e92fd-118">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
