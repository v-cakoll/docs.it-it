---
title: Metodo ICorDebugThread::GetActiveFrame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 441f97ebbaf95a8b6b6e14c8372893a83f6299a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="faa86-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="faa86-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="faa86-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) su questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="faa86-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="faa86-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="faa86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="faa86-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="faa86-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="faa86-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa86-107">Note</span><span class="sxs-lookup"><span data-stu-id="faa86-107">Remarks</span></span>  
 <span data-ttu-id="faa86-108">Il `ppFrame` parametro è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="faa86-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa86-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faa86-109">Requirements</span></span>  
 <span data-ttu-id="faa86-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faa86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa86-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="faa86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faa86-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faa86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faa86-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
