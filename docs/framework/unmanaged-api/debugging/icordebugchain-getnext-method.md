---
title: Metodo ICorDebugChain::GetNext
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839052b72d908e48a4b6f88dab05ec3c3d575d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405411"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="010f1-102">Metodo ICorDebugChain::GetNext</span><span class="sxs-lookup"><span data-stu-id="010f1-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="010f1-103">Ottiene la catena di frame successiva per il thread.</span><span class="sxs-lookup"><span data-stu-id="010f1-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="010f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="010f1-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="010f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="010f1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="010f1-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la successiva catena di frame per il thread.</span><span class="sxs-lookup"><span data-stu-id="010f1-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="010f1-107">Se si tratta dell'ultima catena `ppChain` è null.</span><span class="sxs-lookup"><span data-stu-id="010f1-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="010f1-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="010f1-108">Requirements</span></span>  
 <span data-ttu-id="010f1-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="010f1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="010f1-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="010f1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="010f1-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="010f1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="010f1-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="010f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
