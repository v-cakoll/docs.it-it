---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a9d483e101fdb94a43055b6081fcc31a458a1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="7ffe9-102">Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="7ffe9-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="7ffe9-103">Il [strumento Type Library Exporter](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef.</span><span class="sxs-lookup"><span data-stu-id="7ffe9-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="7ffe9-104">Questa DLL contiene due funzioni di supporto e un'interfaccia che utilizza l'utilità di esportazione durante il processo di conversione da assembly a libreria.</span><span class="sxs-lookup"><span data-stu-id="7ffe9-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ffe9-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7ffe9-105">In This Section</span></span>  
 [<span data-ttu-id="7ffe9-106">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="7ffe9-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="7ffe9-107">Fornisce informazioni di localizzazione e del sistema operativo per una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7ffe9-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="7ffe9-108">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="7ffe9-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="7ffe9-109">Carica una libreria dei tipi tramite un'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere gli eventuali librerie dei tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7ffe9-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="7ffe9-110">Interfaccia ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="7ffe9-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="7ffe9-111">Fornisce il [metodo ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7ffe9-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
