---
title: Enumerazione CLRDataEnumMemoryFlags
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80ea3afef4aee51760e3a2ce6a2b895bca4a6ec5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224066"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="c4c2b-102">Enumerazione CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="c4c2b-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="c4c2b-103">Indica una chiamata a quali aree di memoria di [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) deve includere (metodo).</span><span class="sxs-lookup"><span data-stu-id="c4c2b-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c2b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4c2b-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c4c2b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c4c2b-105">Members</span></span>  
  
|<span data-ttu-id="c4c2b-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4c2b-106">Member</span></span>|<span data-ttu-id="c4c2b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4c2b-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="c4c2b-108">Un minidump, vale a dire, un dump di memoria di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="c4c2b-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="c4c2b-109">Un dump di heap complete.</span><span class="sxs-lookup"><span data-stu-id="c4c2b-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4c2b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4c2b-110">Requirements</span></span>  
 <span data-ttu-id="c4c2b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4c2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c2b-112">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c4c2b-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c4c2b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c2b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4c2b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c2b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4c2b-115">See also</span></span>

- [<span data-ttu-id="c4c2b-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="c4c2b-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
