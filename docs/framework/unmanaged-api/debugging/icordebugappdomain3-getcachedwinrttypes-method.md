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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782a6cf70aa3e3446d8da3160712d57245afe176
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405525"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="710be-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="710be-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="710be-103">Ottiene un enumeratore per tutti memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.</span><span class="sxs-lookup"><span data-stu-id="710be-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="710be-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="710be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="710be-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="710be-106">[out] Un puntatore a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) oggetto dell'interfaccia che può enumerare le rappresentazioni di gestito [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="710be-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="710be-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="710be-107">Requirements</span></span>  
 <span data-ttu-id="710be-108">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710be-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="710be-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="710be-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="710be-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="710be-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="710be-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710be-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="710be-112">See Also</span></span>  
 [<span data-ttu-id="710be-113">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="710be-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
