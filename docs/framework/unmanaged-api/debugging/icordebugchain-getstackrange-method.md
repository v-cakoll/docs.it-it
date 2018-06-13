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
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402470"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="a6dd0-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="a6dd0-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="a6dd0-103">Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dd0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6dd0-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6dd0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6dd0-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="a6dd0-106">[out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo iniziale del segmento di stack.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="a6dd0-107">[out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo finale del segmento di stack.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6dd0-108">Note</span><span class="sxs-lookup"><span data-stu-id="a6dd0-108">Remarks</span></span>  
 <span data-ttu-id="a6dd0-109">L'intervallo numerico è significativo solo per il confronto di percorsi dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="a6dd0-110">È possibile apportare ipotesi in merito a ciò che effettivamente è memorizzato nello stack.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6dd0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6dd0-111">Requirements</span></span>  
 <span data-ttu-id="a6dd0-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6dd0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6dd0-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a6dd0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6dd0-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a6dd0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6dd0-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dd0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
