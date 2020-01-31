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
ms.openlocfilehash: de0e07429187f1ec484942d522cdf57f819d553a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789289"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="e1230-102">Enumerazione CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="e1230-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="e1230-103">Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="e1230-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1230-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1230-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="e1230-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e1230-105">Members</span></span>  
  
|<span data-ttu-id="e1230-106">Nome membro</span><span class="sxs-lookup"><span data-stu-id="e1230-106">Member name</span></span>|<span data-ttu-id="e1230-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1230-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="e1230-108">In un'app di Windows 8. x Store, l'uso delle immagini dalla cache delle immagini native locale è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="e1230-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="e1230-109">In un'applicazione desktop questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e1230-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1230-110">Note</span><span class="sxs-lookup"><span data-stu-id="e1230-110">Remarks</span></span>  
 <span data-ttu-id="e1230-111">L'enumerazione `CorDebugNGENPolicy` viene utilizzata dal metodo [ICorDebugProcess5:: EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e1230-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="e1230-112">La disabilitazione dell'utilizzo di immagini dalla cache delle immagini native locale garantisce un'esperienza di debug coerente garantendo che il debugger carichi immagini compilate tramite JIT sottoposte a debug anziché immagini native ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="e1230-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1230-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e1230-113">Requirements</span></span>  
 <span data-ttu-id="e1230-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1230-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1230-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1230-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1230-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1230-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1230-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1230-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1230-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1230-118">See also</span></span>

- [<span data-ttu-id="e1230-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="e1230-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
