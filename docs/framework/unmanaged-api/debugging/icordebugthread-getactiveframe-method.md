---
title: Metodo ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1bbe5674ba11b5ee6033c65f229d698eff15ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420641"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="c270b-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="c270b-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="c270b-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) su questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c270b-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c270b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c270b-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c270b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c270b-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="c270b-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="c270b-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c270b-107">Note</span><span class="sxs-lookup"><span data-stu-id="c270b-107">Remarks</span></span>  
 <span data-ttu-id="c270b-108">Il `ppFrame` parametro è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="c270b-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c270b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c270b-109">Requirements</span></span>  
 <span data-ttu-id="c270b-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c270b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c270b-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c270b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c270b-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c270b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c270b-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c270b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
