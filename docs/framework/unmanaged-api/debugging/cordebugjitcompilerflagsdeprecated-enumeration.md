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
ms.openlocfilehash: d731b12ddf195137ff38d32ab0ca52aa90f48d4e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132789"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="61b24-102">Enumerazione CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="61b24-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="61b24-103">Questa enumerazione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="61b24-103">This enumeration is obsolete.</span></span> <span data-ttu-id="61b24-104">Usare invece il membro `CORDEBUG_JIT_DEFAULT` dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="61b24-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b24-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61b24-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="61b24-106">Members</span><span class="sxs-lookup"><span data-stu-id="61b24-106">Members</span></span>  
  
|<span data-ttu-id="61b24-107">Member</span><span class="sxs-lookup"><span data-stu-id="61b24-107">Member</span></span>|<span data-ttu-id="61b24-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61b24-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="61b24-109">In alternativa, utilizzare `CORDEBUG_JIT_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="61b24-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61b24-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61b24-110">Requirements</span></span>  
 <span data-ttu-id="61b24-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61b24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b24-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b24-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b24-114">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="61b24-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b24-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61b24-115">See also</span></span>

- [<span data-ttu-id="61b24-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="61b24-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
