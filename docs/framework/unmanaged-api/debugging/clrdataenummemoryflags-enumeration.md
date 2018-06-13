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
ms.openlocfilehash: a19c6f22ee9fbe7eb1019a0b799d63e4ee650e98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406819"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="b3451-102">Enumerazione CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="b3451-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="b3451-103">Indica le aree di memoria di una chiamata al [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) deve includere metodo.</span><span class="sxs-lookup"><span data-stu-id="b3451-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3451-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3451-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b3451-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b3451-105">Members</span></span>  
  
|<span data-ttu-id="b3451-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b3451-106">Member</span></span>|<span data-ttu-id="b3451-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3451-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="b3451-108">Un minidump, vale a dire un dump di memoria di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="b3451-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="b3451-109">Un dump di heap complete.</span><span class="sxs-lookup"><span data-stu-id="b3451-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3451-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3451-110">Requirements</span></span>  
 <span data-ttu-id="b3451-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3451-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3451-112">**Intestazione:** Clrdata. idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="b3451-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b3451-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b3451-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3451-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3451-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3451-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3451-115">See Also</span></span>  
 [<span data-ttu-id="b3451-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b3451-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
