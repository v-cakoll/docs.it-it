---
title: Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886f78a0561ebbd5470b7932123f67975d650693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197347"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="136f8-102">Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="136f8-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="136f8-103">Enumera aree specifiche della memoria.</span><span class="sxs-lookup"><span data-stu-id="136f8-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="136f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="136f8-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="136f8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="136f8-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="136f8-106">[in] Un puntatore a un [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) istanza che viene chiamato da questo metodo per ogni area di memoria in fase di enumerazione per notificare al debugger del risultato.</span><span class="sxs-lookup"><span data-stu-id="136f8-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="136f8-107">L'enumerazione delle aree di memoria continua anche se il callback indica un errore.</span><span class="sxs-lookup"><span data-stu-id="136f8-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="136f8-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="136f8-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="136f8-109">[in] Valore di [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumerazione che specifica le aree di memoria da enumerare.</span><span class="sxs-lookup"><span data-stu-id="136f8-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="136f8-110">Note</span><span class="sxs-lookup"><span data-stu-id="136f8-110">Remarks</span></span>  
 <span data-ttu-id="136f8-111">Questo metodo Usa l'oggetto specificato [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) istanza per notificare i risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="136f8-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="136f8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="136f8-112">Requirements</span></span>  
 <span data-ttu-id="136f8-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="136f8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="136f8-114">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="136f8-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="136f8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="136f8-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="136f8-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="136f8-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="136f8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="136f8-117">See also</span></span>

- [<span data-ttu-id="136f8-118">Interfaccia ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="136f8-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
