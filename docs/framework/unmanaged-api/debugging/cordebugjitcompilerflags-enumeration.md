---
title: Enumerazione CorDebugJITCompilerFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugJITCompilerFlags
helpviewer_keywords: CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfb78a160a7a6b9f50174fc8bb177cfd8d3f9383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="1fada-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="1fada-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="1fada-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="1fada-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fada-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fada-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1fada-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1fada-105">Members</span></span>  
  
|<span data-ttu-id="1fada-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1fada-106">Member</span></span>|<span data-ttu-id="1fada-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fada-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="1fada-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e che consente ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1fada-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="1fada-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disattivare le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1fada-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="1fada-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, disabilitare le ottimizzazioni e Abilita modifica e continuazione tecnologie.</span><span class="sxs-lookup"><span data-stu-id="1fada-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1fada-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fada-111">Requirements</span></span>  
 <span data-ttu-id="1fada-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fada-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fada-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1fada-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fada-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fada-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fada-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fada-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fada-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fada-116">See Also</span></span>  
 [<span data-ttu-id="1fada-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="1fada-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
