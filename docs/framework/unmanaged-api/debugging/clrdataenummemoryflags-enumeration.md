---
title: Enumerazione CLRDataEnumMemoryFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataEnumMemoryFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLRDataEnumMemoryFlags
helpviewer_keywords: CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c88fe4e6bcbe4f2ec3f13c08450f7dea44ccdbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="2e343-102">Enumerazione CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="2e343-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="2e343-103">Indica le aree di memoria di una chiamata al [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) deve includere metodo.</span><span class="sxs-lookup"><span data-stu-id="2e343-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e343-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e343-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="2e343-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2e343-105">Members</span></span>  
  
|<span data-ttu-id="2e343-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2e343-106">Member</span></span>|<span data-ttu-id="2e343-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e343-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="2e343-108">Un minidump, vale a dire un dump di memoria di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="2e343-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="2e343-109">Un dump di heap complete.</span><span class="sxs-lookup"><span data-stu-id="2e343-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e343-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e343-110">Requirements</span></span>  
 <span data-ttu-id="2e343-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e343-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e343-112">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="2e343-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2e343-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e343-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e343-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e343-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e343-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e343-115">See Also</span></span>  
 [<span data-ttu-id="2e343-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2e343-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
