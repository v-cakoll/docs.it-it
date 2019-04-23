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
ms.openlocfilehash: 73a08e83d67c973294938a030b95b906aec6be6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126607"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="96435-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="96435-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="96435-103">Ottiene un enumeratore per tutte le cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.</span><span class="sxs-lookup"><span data-stu-id="96435-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96435-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96435-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="96435-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96435-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="96435-106">[out] Un puntatore a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) oggetto di interfaccia in grado di enumerare le rappresentazioni di gestito [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96435-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96435-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96435-107">Requirements</span></span>  
 <span data-ttu-id="96435-108">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96435-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="96435-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96435-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96435-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96435-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96435-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96435-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96435-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96435-112">See also</span></span>

- [<span data-ttu-id="96435-113">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="96435-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
