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
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132402"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="5a344-102">Enumerazione CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="5a344-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="5a344-103">Indica le aree di memoria che devono essere incluse in una chiamata al metodo [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5a344-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a344-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a344-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5a344-105">Members</span><span class="sxs-lookup"><span data-stu-id="5a344-105">Members</span></span>  
  
|<span data-ttu-id="5a344-106">Member</span><span class="sxs-lookup"><span data-stu-id="5a344-106">Member</span></span>|<span data-ttu-id="5a344-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a344-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="5a344-108">Minidump, ovvero un dump di memoria sparse.</span><span class="sxs-lookup"><span data-stu-id="5a344-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="5a344-109">Dump completo dell'heap.</span><span class="sxs-lookup"><span data-stu-id="5a344-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a344-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a344-110">Requirements</span></span>  
 <span data-ttu-id="5a344-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a344-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a344-112">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="5a344-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5a344-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a344-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a344-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a344-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a344-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a344-115">See also</span></span>

- [<span data-ttu-id="5a344-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="5a344-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
