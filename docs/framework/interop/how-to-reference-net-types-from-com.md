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
ms.openlocfilehash: 081548f9004d2fedf4d49845d3f44d4609fa508e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626313"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="1719b-102">Procedura: Fare riferimento a tipi .NET da COM</span><span class="sxs-lookup"><span data-stu-id="1719b-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="1719b-103">Dal punto di vista del codice client e server, le differenze tra COM e .NET Framework sono in gran parte invisibili.</span><span class="sxs-lookup"><span data-stu-id="1719b-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="1719b-104">I client di Microsoft Visual Basic possono visualizzare un oggetto .NET nel Visualizzatore oggetti, che espone i metodi e la sintassi, le proprietà e i campi dell'oggetto esattamente come se si trattasse di un normale oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="1719b-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="1719b-105">Il processo per l'importazione di una libreria dei tipi è leggermente più complesso per i client C++, anche se si usano gli stessi strumenti per esportare i metadati in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="1719b-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="1719b-106">Per fare riferimento a membri di oggetti .NET da un client C++ non gestito, fare riferimento al file TLB (prodotto con Tlbexp.exe) con la direttiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="1719b-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="1719b-107">Quando si fa riferimento a una libreria dei tipi da C++, è necessario specificare l'opzione **raw_interfaces_only** o importare le definizioni nella libreria di classi di base, Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="1719b-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="1719b-108">Per importare una libreria</span><span class="sxs-lookup"><span data-stu-id="1719b-108">To import a library</span></span>  
  
- <span data-ttu-id="1719b-109">Specificare l'opzione **raw_interfaces_only** nella direttiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="1719b-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="1719b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1719b-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="1719b-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="1719b-111">-or-</span></span>  
  
- <span data-ttu-id="1719b-112">Includere una direttiva #import per Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="1719b-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="1719b-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1719b-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1719b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1719b-114">See also</span></span>

- [<span data-ttu-id="1719b-115">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="1719b-115">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="1719b-116">Registrazione di assembly presso COM</span><span class="sxs-lookup"><span data-stu-id="1719b-116">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="1719b-117">[Chiamata di un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1719b-117">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="1719b-118">[Distribuzione di un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1719b-118">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
