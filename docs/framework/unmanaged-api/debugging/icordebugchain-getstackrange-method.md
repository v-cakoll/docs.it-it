---
title: Metodo ICorDebugChain::GetStackRange
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
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37a9be7924a6d9c1f1d78bd10f9642fff22036bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="eaa7d-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="eaa7d-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="eaa7d-103">Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="eaa7d-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eaa7d-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eaa7d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eaa7d-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="eaa7d-106">[out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo iniziale del segmento di stack.</span><span class="sxs-lookup"><span data-stu-id="eaa7d-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="eaa7d-107">[out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo finale del segmento di stack.</span><span class="sxs-lookup"><span data-stu-id="eaa7d-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa7d-108">Note</span><span class="sxs-lookup"><span data-stu-id="eaa7d-108">Remarks</span></span>  
 <span data-ttu-id="eaa7d-109">L'intervallo numerico è significativo solo per il confronto di percorsi dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="eaa7d-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="eaa7d-110">È possibile apportare ipotesi in merito a ciò che effettivamente è memorizzato nello stack.</span><span class="sxs-lookup"><span data-stu-id="eaa7d-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa7d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eaa7d-111">Requirements</span></span>  
 <span data-ttu-id="eaa7d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaa7d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaa7d-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="eaa7d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaa7d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaa7d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaa7d-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa7d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
