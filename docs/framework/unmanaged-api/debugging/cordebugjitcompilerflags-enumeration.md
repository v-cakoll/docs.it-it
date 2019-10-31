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
ms.openlocfilehash: 739b491d343c0eba76160c15719069ffae385f46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097966"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="f6dc1-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="f6dc1-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="f6dc1-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6dc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6dc1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f6dc1-105">Members</span><span class="sxs-lookup"><span data-stu-id="f6dc1-105">Members</span></span>  
  
|<span data-ttu-id="f6dc1-106">Member</span><span class="sxs-lookup"><span data-stu-id="f6dc1-106">Member</span></span>|<span data-ttu-id="f6dc1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6dc1-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="f6dc1-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e consente le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="f6dc1-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilita le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="f6dc1-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, Disabilita le ottimizzazioni e Abilita le tecnologie di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6dc1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6dc1-111">Requirements</span></span>  
 <span data-ttu-id="f6dc1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6dc1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6dc1-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6dc1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6dc1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6dc1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6dc1-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6dc1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6dc1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6dc1-116">See also</span></span>

- [<span data-ttu-id="f6dc1-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f6dc1-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
