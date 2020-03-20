---
title: dati di marshalling con interoperabilità COM
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: ae41713d5349321725599c0c38d7c6fc515c374b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181378"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="ce17a-102">dati di marshalling con interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="ce17a-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="ce17a-103">Grazie all'interoperabilità COM, è possibile usare oggetti COM dal codice gestito ed esporre oggetti gestiti a COM.</span><span class="sxs-lookup"><span data-stu-id="ce17a-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="ce17a-104">Il supporto per effettuare il marshalling dei dati verso e da COM è estensivo e garantisce sempre il comportamento di marshalling corretto.</span><span class="sxs-lookup"><span data-stu-id="ce17a-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="ce17a-105">Windows SDK include i seguenti strumenti di interoperabilità COM:</span><span class="sxs-lookup"><span data-stu-id="ce17a-105">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="ce17a-106">[Utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), che consente di convertire una libreria dei tipi COM in un assembly di interoperabilità,</span><span class="sxs-lookup"><span data-stu-id="ce17a-106">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="ce17a-107">dal quale, con il servizio di marshalling di interoperabilità, vengono generati wrapper per il marshalling dei dati tra memoria gestita e non gestita.</span><span class="sxs-lookup"><span data-stu-id="ce17a-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="ce17a-108">[Utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), che consente di generare una libreria dei tipi COM da un assembly e un wrapper per l'esecuzione del marshalling durante le chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="ce17a-108">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="ce17a-109">Le sezioni seguenti riportano collegamenti ad argomenti che descrivono i processi per la personalizzazione dei wrapper di interoperabilità quando è possibile o necessario fornire altre informazioni sui tipi al gestore di marshalling.</span><span class="sxs-lookup"><span data-stu-id="ce17a-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce17a-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ce17a-110">In This Section</span></span>  
<span data-ttu-id="ce17a-111">[Procedura: creare manualmente wrapperHow to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Viene descritto come creare manualmente un wrapper COM nel codice sorgente gestito.</span><span class="sxs-lookup"><span data-stu-id="ce17a-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Describes how to create a COM wrapper manually in managed source code.</span></span>

 [<span data-ttu-id="ce17a-112">Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="ce17a-112">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="ce17a-113">Descrive come eseguire la migrazione di codice gestito DCOM in WCF per la soluzione più sicura.</span><span class="sxs-lookup"><span data-stu-id="ce17a-113">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ce17a-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ce17a-114">Related Sections</span></span>  
 <span data-ttu-id="ce17a-115">[Tipi di dati COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-115">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-116">Fornisce i tipi di dati gestiti e non gestiti corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ce17a-116">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="ce17a-117">[Personalizzazione di wrapper COM richiamabili](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-117">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-118">Descrive come effettuare esplicitamente il marshalling dei tipi di dati tramite l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ce17a-118">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="ce17a-119">[Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-119">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-120">Descrive come regolare il comportamento del marshalling dei tipi in un assembly di interoperabilità e come definire manualmente i tipi COM.</span><span class="sxs-lookup"><span data-stu-id="ce17a-120">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="ce17a-121">[Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-121">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-122">Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce17a-122">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="ce17a-123">[Riepilogo della conversione da assembly a libreria dei tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-123">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-124">Descrive il processo di conversione eseguito in caso di esportazione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="ce17a-124">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="ce17a-125">[Riepilogo della conversione da libreria dei tipi ad assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-125">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-126">Descrive il processo di conversione eseguito in caso di importazione da libreria dei tipi ad assembly.</span><span class="sxs-lookup"><span data-stu-id="ce17a-126">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="ce17a-127">[Interoperabilità tramite tipi generici](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce17a-127">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="ce17a-128">Descrive le azioni supportate quando si usano tipi generici per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="ce17a-128">Describes which actions are supported when using generic types for COM interoperability.</span></span>
