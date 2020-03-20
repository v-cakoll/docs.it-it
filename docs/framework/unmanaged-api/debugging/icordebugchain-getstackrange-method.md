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
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178963"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="b2889-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="b2889-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="b2889-103">Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="b2889-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2889-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2889-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2889-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2889-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="b2889-106">[fuori] Puntatore a `CORDB_ADDRESS` un valore che è l'indirizzo iniziale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="b2889-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="b2889-107">[fuori] Puntatore a `CORDB_ADDRESS` un valore che è l'indirizzo finale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="b2889-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2889-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2889-108">Remarks</span></span>  
 <span data-ttu-id="b2889-109">L'intervallo numerico è significativo solo per il confronto delle posizioni dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="b2889-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="b2889-110">Non è possibile fare supposizioni su ciò che viene effettivamente archiviato nello stack.</span><span class="sxs-lookup"><span data-stu-id="b2889-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2889-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2889-111">Requirements</span></span>  
 <span data-ttu-id="b2889-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2889-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2889-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2889-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2889-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2889-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2889-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2889-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
