---
title: Enumerazione CorDebugInternalFrameType
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b42a7fc54af56149b602b337e4a6c853c270cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406357"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="2c92c-102">Enumerazione CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="2c92c-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="2c92c-103">Identifica il tipo di stack frame.</span><span class="sxs-lookup"><span data-stu-id="2c92c-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="2c92c-104">Questa enumerazione viene utilizzata per la [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="2c92c-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c92c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c92c-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="2c92c-106">Membri</span><span class="sxs-lookup"><span data-stu-id="2c92c-106">Members</span></span>  
  
|<span data-ttu-id="2c92c-107">Membro</span><span class="sxs-lookup"><span data-stu-id="2c92c-107">Member</span></span>|<span data-ttu-id="2c92c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c92c-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="2c92c-109">Valore null.</span><span class="sxs-lookup"><span data-stu-id="2c92c-109">A null value.</span></span> <span data-ttu-id="2c92c-110">Il `ICorDebugInternalFrame::GetFrameType` metodo non restituisce mai questo valore.</span><span class="sxs-lookup"><span data-stu-id="2c92c-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="2c92c-111">Un frame di uno stub a gestito.</span><span class="sxs-lookup"><span data-stu-id="2c92c-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="2c92c-112">Un frame di stub non gestito a gestito.</span><span class="sxs-lookup"><span data-stu-id="2c92c-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="2c92c-113">Una transizione tra i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c92c-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="2c92c-114">Una chiamata al metodo leggero.</span><span class="sxs-lookup"><span data-stu-id="2c92c-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="2c92c-115">Inizio della valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="2c92c-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="2c92c-116">Una chiamata interna di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="2c92c-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="2c92c-117">Inizio dell'inizializzazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="2c92c-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="2c92c-118">Eccezione che viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2c92c-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="2c92c-119">Un frame utilizzato per la sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="2c92c-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="2c92c-120">Il runtime è un metodo di compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="2c92c-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c92c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c92c-121">Requirements</span></span>  
 <span data-ttu-id="2c92c-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c92c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c92c-123">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2c92c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c92c-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2c92c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c92c-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c92c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c92c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c92c-126">See Also</span></span>  
 [<span data-ttu-id="2c92c-127">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2c92c-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
