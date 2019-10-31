---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypes
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: 89f45208550d49f214e763728ddc9eb1bfcd9800
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088966"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="16782-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="16782-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="16782-103">Ottiene un enumeratore per tutti i tipi di Windows Runtime memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="16782-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16782-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16782-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="16782-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16782-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="16782-106">out Puntatore a un oggetto interfaccia [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) in grado di enumerare le rappresentazioni gestite dei tipi Windows Runtime attualmente caricati nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="16782-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16782-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16782-107">Requirements</span></span>  
 <span data-ttu-id="16782-108">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="16782-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="16782-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16782-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16782-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16782-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16782-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16782-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16782-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16782-112">See also</span></span>

- [<span data-ttu-id="16782-113">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="16782-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
