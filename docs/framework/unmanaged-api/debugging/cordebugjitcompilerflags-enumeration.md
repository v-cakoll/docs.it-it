---
title: Enumerazione CorDebugJITCompilerFlags
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 512122d264e0817b89e8a371f57f11d31f7c4380
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639638"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="3f6a2-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="3f6a2-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="3f6a2-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f6a2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3f6a2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3f6a2-105">Members</span></span>  
  
|<span data-ttu-id="3f6a2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3f6a2-106">Member</span></span>|<span data-ttu-id="3f6a2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f6a2-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="3f6a2-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e consentire l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="3f6a2-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilitare le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="3f6a2-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, disabilitare le ottimizzazioni e Abilita modifica e continuazione tecnologie.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f6a2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f6a2-111">Requirements</span></span>  
 <span data-ttu-id="3f6a2-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6a2-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f6a2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f6a2-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f6a2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f6a2-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6a2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f6a2-116">See also</span></span>
- [<span data-ttu-id="3f6a2-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3f6a2-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
