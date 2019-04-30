---
title: Metodo ICorDebugChain::GetStackRange
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989456"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="45379-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="45379-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="45379-103">Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="45379-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45379-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45379-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45379-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45379-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="45379-106">[out] Un puntatore a un `CORDB_ADDRESS` valore, ovvero l'indirizzo iniziale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="45379-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="45379-107">[out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo finale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="45379-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45379-108">Note</span><span class="sxs-lookup"><span data-stu-id="45379-108">Remarks</span></span>  
 <span data-ttu-id="45379-109">L'intervallo numerico è significativa solo per il confronto dei percorsi dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="45379-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="45379-110">È possibile fare supposizioni su ciò che effettivamente è memorizzato nello stack.</span><span class="sxs-lookup"><span data-stu-id="45379-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45379-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45379-111">Requirements</span></span>  
 <span data-ttu-id="45379-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45379-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45379-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45379-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45379-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45379-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45379-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45379-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
