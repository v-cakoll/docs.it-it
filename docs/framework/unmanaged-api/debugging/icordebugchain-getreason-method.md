---
title: Metodo ICorDebugChain::GetReason
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d02a68e80e34be906e9fe09f3457a0f2214c6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405067"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="16cd8-102">Metodo ICorDebugChain::GetReason</span><span class="sxs-lookup"><span data-stu-id="16cd8-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="16cd8-103">Ottiene il motivo per la creazione di questa catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="16cd8-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16cd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16cd8-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16cd8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16cd8-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="16cd8-106">[out] Un puntatore a un valore (una combinazione bit per bit) dell'enumerazione CorDebugChainReason che indica il motivo per la creazione di questa catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="16cd8-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16cd8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16cd8-107">Requirements</span></span>  
 <span data-ttu-id="16cd8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16cd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16cd8-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="16cd8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16cd8-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="16cd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16cd8-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16cd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
