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
ms.openlocfilehash: 4e3891996af5945ed95c8c37dddfee5c446db248
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789114"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="9317d-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="9317d-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="9317d-103">Fornisce un metodo di callback per [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="9317d-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9317d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9317d-104">Methods</span></span>  
  
|<span data-ttu-id="9317d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9317d-105">Method</span></span>|<span data-ttu-id="9317d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9317d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9317d-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="9317d-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="9317d-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="9317d-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9317d-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9317d-109">Requirements</span></span>  
 <span data-ttu-id="9317d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9317d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9317d-111">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="9317d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9317d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9317d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9317d-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9317d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9317d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9317d-114">See also</span></span>

- [<span data-ttu-id="9317d-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9317d-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
