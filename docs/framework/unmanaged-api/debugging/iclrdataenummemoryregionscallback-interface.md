---
title: Interfaccia ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225430"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="f311d-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="f311d-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="f311d-103">Fornisce un metodo di callback [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="f311d-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f311d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f311d-104">Methods</span></span>  
  
|<span data-ttu-id="f311d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f311d-105">Method</span></span>|<span data-ttu-id="f311d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f311d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f311d-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="f311d-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="f311d-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="f311d-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f311d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f311d-109">Requirements</span></span>  
 <span data-ttu-id="f311d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f311d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f311d-111">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f311d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f311d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f311d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f311d-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f311d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f311d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f311d-114">See also</span></span>

- [<span data-ttu-id="f311d-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f311d-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
