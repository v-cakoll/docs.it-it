---
title: Metodo ICorDebugChain::EnumerateFrames
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="8ab2a-102">Metodo ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="8ab2a-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="8ab2a-103">Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ab2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ab2a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ab2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ab2a-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="8ab2a-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFrameEnum che è l'enumeratore per gli stack frame.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ab2a-107">Note</span><span class="sxs-lookup"><span data-stu-id="8ab2a-107">Remarks</span></span>  
 <span data-ttu-id="8ab2a-108">La catena rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="8ab2a-109">Il `EnumerateFrames` metodo deve essere chiamato solo per le catene gestite.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="8ab2a-110">L'API di debug non fornisce metodi per ottenere i frame contenuti nelle catene non gestite.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="8ab2a-111">Il debugger deve utilizzare altri mezzi per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="8ab2a-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ab2a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ab2a-112">Requirements</span></span>  
 <span data-ttu-id="8ab2a-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ab2a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ab2a-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8ab2a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ab2a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ab2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ab2a-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ab2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
