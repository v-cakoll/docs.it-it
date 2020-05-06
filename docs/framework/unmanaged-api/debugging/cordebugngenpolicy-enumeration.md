---
title: Enumerazione CorDebugNGenPolicy
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 036d3f12b38c19259fefaba674d0f9025a58d688
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795755"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="0c026-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="0c026-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="0c026-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="0c026-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c026-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c026-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="0c026-105">Members</span><span class="sxs-lookup"><span data-stu-id="0c026-105">Members</span></span>  
  
|<span data-ttu-id="0c026-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="0c026-106">Member name</span></span>|<span data-ttu-id="0c026-107">Description</span><span class="sxs-lookup"><span data-stu-id="0c026-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="0c026-108">In un'app di Windows 8. x Store, l'uso delle immagini dalla cache delle immagini native locale è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0c026-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="0c026-109">In un'applicazione desktop questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="0c026-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c026-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c026-110">Remarks</span></span>  
 <span data-ttu-id="0c026-111">L' `CorDebugNGENPolicy` enumerazione viene utilizzata dal metodo [ICorDebugProcess5:: EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0c026-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="0c026-112">La disabilitazione dell'utilizzo di immagini dalla cache delle immagini native locale garantisce un'esperienza di debug coerente garantendo che il debugger carichi immagini compilate tramite JIT sottoposte a debug anziché immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="0c026-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c026-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c026-113">Requirements</span></span>  
 <span data-ttu-id="0c026-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c026-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c026-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c026-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c026-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c026-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c026-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c026-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c026-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c026-118">See also</span></span>

- [<span data-ttu-id="0c026-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="0c026-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
