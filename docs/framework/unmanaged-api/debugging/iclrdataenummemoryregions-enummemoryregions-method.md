---
title: Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1393c5c803020339ef998a57b87ad495220c1046
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="2f581-102">Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="2f581-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="2f581-103">Enumera le aree di memoria specificate.</span><span class="sxs-lookup"><span data-stu-id="2f581-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f581-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f581-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f581-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f581-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="2f581-106">[in] Un puntatore a un [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) istanza che viene chiamato da questo metodo per ogni area di memoria per notificare al debugger del risultato enumerato.</span><span class="sxs-lookup"><span data-stu-id="2f581-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="2f581-107">L'enumerazione delle aree di memoria continua anche se il callback indica un errore.</span><span class="sxs-lookup"><span data-stu-id="2f581-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="2f581-108">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="2f581-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="2f581-109">[in] Il valore di [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumerazione che specifica le aree di memoria da enumerare.</span><span class="sxs-lookup"><span data-stu-id="2f581-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f581-110">Note</span><span class="sxs-lookup"><span data-stu-id="2f581-110">Remarks</span></span>  
 <span data-ttu-id="2f581-111">Questo metodo utilizza l'oggetto specificato [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) istanza per notificare i risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="2f581-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f581-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f581-112">Requirements</span></span>  
 <span data-ttu-id="2f581-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f581-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f581-114">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="2f581-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2f581-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f581-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f581-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f581-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f581-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f581-117">See Also</span></span>  
 [<span data-ttu-id="2f581-118">ICLRDataEnumMemoryRegions (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2f581-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
