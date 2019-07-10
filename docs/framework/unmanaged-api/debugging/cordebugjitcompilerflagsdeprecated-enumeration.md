---
title: Enumerazione CorDebugJITCompilerFlagsDeprecated
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd0def06defa677ddde798106c299ed909cd4ce1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739779"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="2c582-102">Enumerazione CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="2c582-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="2c582-103">Questa enumerazione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="2c582-103">This enumeration is obsolete.</span></span> <span data-ttu-id="2c582-104">Usare la `CORDEBUG_JIT_DEFAULT` membro della [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione invece.</span><span class="sxs-lookup"><span data-stu-id="2c582-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c582-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c582-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="2c582-106">Membri</span><span class="sxs-lookup"><span data-stu-id="2c582-106">Members</span></span>  
  
|<span data-ttu-id="2c582-107">Member</span><span class="sxs-lookup"><span data-stu-id="2c582-107">Member</span></span>|<span data-ttu-id="2c582-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c582-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="2c582-109">In alternativa, utilizzare `CORDEBUG_JIT_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="2c582-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c582-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c582-110">Requirements</span></span>  
 <span data-ttu-id="2c582-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c582-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c582-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c582-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c582-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c582-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c582-114">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2c582-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c582-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c582-115">See also</span></span>

- [<span data-ttu-id="2c582-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2c582-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
