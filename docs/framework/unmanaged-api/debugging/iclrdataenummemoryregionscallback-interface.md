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
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860655"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="c8207-102">Interfaccia ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="c8207-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="c8207-103">Fornisce un metodo di callback per [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="c8207-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8207-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c8207-104">Methods</span></span>  
  
|<span data-ttu-id="c8207-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c8207-105">Method</span></span>|<span data-ttu-id="c8207-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8207-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8207-107">Metodo EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="c8207-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="c8207-108">Chiamato da `ICLRDataEnumMemoryRegions::EnumMemoryRegions` per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="c8207-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8207-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8207-109">Requirements</span></span>  
 <span data-ttu-id="c8207-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8207-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8207-111">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c8207-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c8207-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8207-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8207-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8207-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8207-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8207-114">See also</span></span>

- [<span data-ttu-id="c8207-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c8207-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
