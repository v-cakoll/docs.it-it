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
ms.openlocfilehash: 5835da6ee20673c2662f1166d304a45ca3e9daeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405320"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="993fe-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="993fe-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="993fe-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="993fe-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="993fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="993fe-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="993fe-105">Membri</span><span class="sxs-lookup"><span data-stu-id="993fe-105">Members</span></span>  
  
|<span data-ttu-id="993fe-106">Membro</span><span class="sxs-lookup"><span data-stu-id="993fe-106">Member</span></span>|<span data-ttu-id="993fe-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="993fe-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="993fe-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e che consente ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="993fe-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="993fe-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disattivare le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="993fe-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="993fe-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, disabilitare le ottimizzazioni e Abilita modifica e continuazione tecnologie.</span><span class="sxs-lookup"><span data-stu-id="993fe-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="993fe-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="993fe-111">Requirements</span></span>  
 <span data-ttu-id="993fe-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="993fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="993fe-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="993fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="993fe-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="993fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="993fe-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="993fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993fe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="993fe-116">See Also</span></span>  
 [<span data-ttu-id="993fe-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="993fe-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
