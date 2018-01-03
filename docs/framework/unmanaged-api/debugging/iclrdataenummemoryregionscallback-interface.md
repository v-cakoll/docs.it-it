---
title: Interfaccia ICLRDataEnumMemoryRegionsCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords: ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 091f5345461ebe5054e769ae9d051ef2e0737ffb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="47678-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="47678-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="47678-103">Fornisce un metodo di callback per [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="47678-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47678-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="47678-104">Methods</span></span>  
  
|<span data-ttu-id="47678-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="47678-105">Method</span></span>|<span data-ttu-id="47678-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47678-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47678-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="47678-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="47678-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="47678-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47678-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47678-109">Requirements</span></span>  
 <span data-ttu-id="47678-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47678-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47678-111">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="47678-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="47678-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47678-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47678-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47678-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47678-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47678-114">See Also</span></span>  
 [<span data-ttu-id="47678-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="47678-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
