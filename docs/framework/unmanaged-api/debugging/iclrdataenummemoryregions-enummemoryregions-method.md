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
ms.openlocfilehash: 693ec07176f80711709cd9b85c6886bea8be74b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122958"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="518ec-102">Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="518ec-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="518ec-103">Enumera le aree di memoria specificate.</span><span class="sxs-lookup"><span data-stu-id="518ec-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="518ec-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="518ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="518ec-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="518ec-106">in Puntatore a un'istanza di [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) che viene chiamata da questo metodo per ogni area di memoria enumerata per notificare al debugger il risultato.</span><span class="sxs-lookup"><span data-stu-id="518ec-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="518ec-107">L'enumerazione delle aree di memoria continua anche se il callback indica un errore.</span><span class="sxs-lookup"><span data-stu-id="518ec-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="518ec-108">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="518ec-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="518ec-109">in Valore dell'enumerazione [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) che specifica le aree di memoria da enumerare.</span><span class="sxs-lookup"><span data-stu-id="518ec-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="518ec-110">Note</span><span class="sxs-lookup"><span data-stu-id="518ec-110">Remarks</span></span>  
 <span data-ttu-id="518ec-111">Questo metodo usa l'istanza di [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) specificata per notificare al chiamante i risultati.</span><span class="sxs-lookup"><span data-stu-id="518ec-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518ec-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="518ec-112">Requirements</span></span>  
 <span data-ttu-id="518ec-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="518ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518ec-114">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="518ec-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="518ec-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="518ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="518ec-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518ec-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518ec-117">See also</span></span>

- [<span data-ttu-id="518ec-118">Interfaccia ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="518ec-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
