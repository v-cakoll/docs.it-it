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
ms.openlocfilehash: 65d7e830b82cc1780826517fe8cff1da0a7d6188
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793899"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="51fe9-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="51fe9-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="51fe9-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="51fe9-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51fe9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51fe9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="51fe9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="51fe9-105">Members</span></span>  
  
|<span data-ttu-id="51fe9-106">Member</span><span class="sxs-lookup"><span data-stu-id="51fe9-106">Member</span></span>|<span data-ttu-id="51fe9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51fe9-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="51fe9-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e consente le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="51fe9-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="51fe9-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilita le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="51fe9-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="51fe9-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, Disabilita le ottimizzazioni e Abilita le tecnologie di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="51fe9-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51fe9-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="51fe9-111">Requirements</span></span>  
 <span data-ttu-id="51fe9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51fe9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51fe9-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51fe9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51fe9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51fe9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51fe9-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fe9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fe9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51fe9-116">See also</span></span>

- [<span data-ttu-id="51fe9-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="51fe9-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
