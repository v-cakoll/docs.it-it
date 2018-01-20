---
title: "dati di marshalling con interoperabilità COM"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 649936abfe149371445c77802bda2e72f558a41d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="7a205-102">dati di marshalling con interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="7a205-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="7a205-103">Grazie all'interoperabilità COM, è possibile usare oggetti COM dal codice gestito ed esporre oggetti gestiti a COM.</span><span class="sxs-lookup"><span data-stu-id="7a205-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="7a205-104">Il supporto per il marshalling dei dati verso e da COM è estensivo e garantisce sempre il comportamento di marshalling corretto.</span><span class="sxs-lookup"><span data-stu-id="7a205-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="7a205-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] include i seguenti strumenti di interoperabilità COM:</span><span class="sxs-lookup"><span data-stu-id="7a205-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="7a205-106">[Utilità di importazione della libreria dei tipi (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), che consente di convertire una libreria dei tipi COM in un assembly di interoperabilità,</span><span class="sxs-lookup"><span data-stu-id="7a205-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="7a205-107">dal quale, con il servizio di marshalling di interoperabilità, vengono generati wrapper per il marshalling dei dati tra memoria gestita e non gestita.</span><span class="sxs-lookup"><span data-stu-id="7a205-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="7a205-108">[Utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che consente di generare una libreria dei tipi COM da un assembly e un wrapper per l'esecuzione del marshalling durante le chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="7a205-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="7a205-109">Nelle sezioni seguenti collegano ad argomenti che descrivono i processi per la personalizzazione di wrapper di interoperabilità quando è possibile o necessario fornire altre informazioni sui tipi al gestore di marshalling.</span><span class="sxs-lookup"><span data-stu-id="7a205-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a205-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7a205-110">In This Section</span></span>  
<span data-ttu-id="7a205-111">[Procedura: creare wrapper manualmente](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="7a205-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="7a205-112">Viene descritto come creare manualmente un wrapper COM nel codice sorgente gestito.</span><span class="sxs-lookup"><span data-stu-id="7a205-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="7a205-113">Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="7a205-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="7a205-114">Viene descritto come eseguire la migrazione di codice gestito DCOM a WCF per la soluzione più sicura.</span><span class="sxs-lookup"><span data-stu-id="7a205-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a205-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7a205-115">Related Sections</span></span>  
 <span data-ttu-id="7a205-116">[Tipi di dati COM](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-116">[COM Data Types](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-117">Fornisce i tipi di dati gestiti e non gestiti corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7a205-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="7a205-118">[Personalizzazione di wrapper COM richiamabili](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-119">Viene descritto come eseguire in modo esplicito il marshalling di tipi di dati tramite il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7a205-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="7a205-120">[Personalizzazione dei Runtime Callable Wrapper](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-121">Descrive come regolare il comportamento del marshalling dei tipi in un assembly di interoperabilità e come definire manualmente i tipi COM.</span><span class="sxs-lookup"><span data-stu-id="7a205-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="7a205-122">[Interoperabilità COM avanzata](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-122">[Advanced COM Interoperability](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-123">Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a205-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="7a205-124">[Riepilogo della conversione da assembly a libreria dei tipi](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-125">Descrive il processo di conversione eseguito in caso di esportazione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7a205-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="7a205-126">[Riepilogo della conversione da libreria dei tipi ad assembly](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-127">Descrive il processo di conversione eseguito in caso di importazione da libreria dei tipi ad assembly.</span><span class="sxs-lookup"><span data-stu-id="7a205-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="7a205-128">[Interoperabilità tramite tipi generici](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a205-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="7a205-129">Descrive le azioni supportate quando si usano tipi generici per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="7a205-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
