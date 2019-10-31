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
ms.openlocfilehash: 826dfceb28512e4fd3157c432b7a4d94fba704fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097866"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="15f39-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="15f39-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="15f39-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="15f39-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15f39-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="15f39-105">Members</span><span class="sxs-lookup"><span data-stu-id="15f39-105">Members</span></span>  
  
|<span data-ttu-id="15f39-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="15f39-106">Member name</span></span>|<span data-ttu-id="15f39-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15f39-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="15f39-108">In un'app [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)], l'uso delle immagini dalla cache delle immagini native locali è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="15f39-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="15f39-109">In un'applicazione desktop questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="15f39-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15f39-110">Note</span><span class="sxs-lookup"><span data-stu-id="15f39-110">Remarks</span></span>  
 <span data-ttu-id="15f39-111">L'enumerazione `CorDebugNGENPolicy` viene utilizzata dal metodo [ICorDebugProcess5:: EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="15f39-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="15f39-112">La disabilitazione dell'utilizzo di immagini dalla cache delle immagini native locale garantisce un'esperienza di debug coerente garantendo che il debugger carichi immagini compilate tramite JIT sottoposte a debug anziché immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="15f39-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f39-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15f39-113">Requirements</span></span>  
 <span data-ttu-id="15f39-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f39-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f39-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15f39-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15f39-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15f39-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15f39-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f39-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f39-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f39-118">See also</span></span>

- [<span data-ttu-id="15f39-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="15f39-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
