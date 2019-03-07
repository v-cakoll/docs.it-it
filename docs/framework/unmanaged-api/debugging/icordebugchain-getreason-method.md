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
ms.openlocfilehash: 48650a370f7d15724e20850e9d3b47dc8215f960
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498354"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="8d5b6-102">Metodo ICorDebugChain::GetReason</span><span class="sxs-lookup"><span data-stu-id="8d5b6-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="8d5b6-103">Ottiene il motivo per la creazione di questa catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d5b6-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d5b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d5b6-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d5b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d5b6-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="8d5b6-106">[out] Un puntatore a un valore (una combinazione bit per bit) dell'enumerazione CorDebugChainReason che indica il motivo per la creazione di questa catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d5b6-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d5b6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d5b6-107">Requirements</span></span>  
 <span data-ttu-id="8d5b6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d5b6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d5b6-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d5b6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d5b6-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d5b6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d5b6-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d5b6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
