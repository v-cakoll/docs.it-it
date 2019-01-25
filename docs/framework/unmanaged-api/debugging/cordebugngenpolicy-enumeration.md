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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ae40916807a86d1c9828080a6cb9e5c1d14c2ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671226"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="3de1d-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="3de1d-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="3de1d-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="3de1d-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3de1d-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="3de1d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3de1d-105">Members</span></span>  
  
|<span data-ttu-id="3de1d-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="3de1d-106">Member name</span></span>|<span data-ttu-id="3de1d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3de1d-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="3de1d-108">In un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, l'uso delle immagini dalla cache delle immagini native locale è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="3de1d-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="3de1d-109">In un'app desktop, questa impostazione ha effetto.</span><span class="sxs-lookup"><span data-stu-id="3de1d-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3de1d-110">Note</span><span class="sxs-lookup"><span data-stu-id="3de1d-110">Remarks</span></span>  
 <span data-ttu-id="3de1d-111">Il `CorDebugNGENPolicy` enumerazione viene utilizzata per il [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3de1d-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="3de1d-112">Disabilitare l'utilizzo delle immagini dalla cache delle immagini native locali fornisce un'esperienza di debug coerente, garantendo che il debugger carica immagini debuggable compilato tramite JIT anziché le immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="3de1d-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de1d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3de1d-113">Requirements</span></span>  
 <span data-ttu-id="3de1d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de1d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3de1d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3de1d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de1d-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de1d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3de1d-118">See also</span></span>
- [<span data-ttu-id="3de1d-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3de1d-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
