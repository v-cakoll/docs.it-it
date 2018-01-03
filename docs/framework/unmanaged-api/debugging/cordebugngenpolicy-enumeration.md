---
title: Enumerazione CorDebugNGenPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugNGenPolicy
helpviewer_keywords: CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89767da7178319ed1add3dda0620062893487bfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="28f47-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="28f47-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="28f47-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="28f47-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28f47-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="28f47-105">Membri</span><span class="sxs-lookup"><span data-stu-id="28f47-105">Members</span></span>  
  
|<span data-ttu-id="28f47-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="28f47-106">Member name</span></span>|<span data-ttu-id="28f47-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28f47-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="28f47-108">In un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, l'utilizzo di immagini dalla cache delle immagini native locali è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="28f47-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="28f47-109">In un'applicazione desktop, questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="28f47-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28f47-110">Note</span><span class="sxs-lookup"><span data-stu-id="28f47-110">Remarks</span></span>  
 <span data-ttu-id="28f47-111">Il `CorDebugNGENPolicy` enumerazione viene utilizzata per la [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="28f47-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="28f47-112">Disabilitare l'utilizzo di immagini dalla cache delle immagini native locali garantisce per un'esperienza di debug coerente, assicurando che il debugger carica le immagini con compilazione JIT debuggable anziché le immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="28f47-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f47-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28f47-113">Requirements</span></span>  
 <span data-ttu-id="28f47-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28f47-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f47-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="28f47-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28f47-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28f47-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28f47-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f47-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28f47-118">See Also</span></span>  
 [<span data-ttu-id="28f47-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="28f47-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
