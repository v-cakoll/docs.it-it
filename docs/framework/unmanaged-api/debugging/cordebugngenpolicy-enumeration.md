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
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599502"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="4cb69-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="4cb69-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="4cb69-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="4cb69-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cb69-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="4cb69-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4cb69-105">Members</span></span>  
  
|<span data-ttu-id="4cb69-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="4cb69-106">Member name</span></span>|<span data-ttu-id="4cb69-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4cb69-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="4cb69-108">In un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, l'uso delle immagini dalla cache delle immagini native locale è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4cb69-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="4cb69-109">In un'app desktop, questa impostazione ha effetto.</span><span class="sxs-lookup"><span data-stu-id="4cb69-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cb69-110">Note</span><span class="sxs-lookup"><span data-stu-id="4cb69-110">Remarks</span></span>  
 <span data-ttu-id="4cb69-111">Il `CorDebugNGENPolicy` enumerazione viene utilizzata per il [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="4cb69-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="4cb69-112">Disabilitare l'utilizzo delle immagini dalla cache delle immagini native locali fornisce un'esperienza di debug coerente, garantendo che il debugger carica immagini debuggable compilato tramite JIT anziché le immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="4cb69-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb69-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cb69-113">Requirements</span></span>  
 <span data-ttu-id="4cb69-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb69-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb69-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cb69-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cb69-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb69-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb69-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb69-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb69-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cb69-118">See also</span></span>

- [<span data-ttu-id="4cb69-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="4cb69-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
