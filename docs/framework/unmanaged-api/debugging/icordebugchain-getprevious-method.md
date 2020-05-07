---
title: Metodo ICorDebugChain::GetPrevious
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
ms.openlocfilehash: a57e73495ac22a25a5f13c06d4c75dee7dde41e0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894627"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="2627d-102">Metodo ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="2627d-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="2627d-103">Ottiene la catena di fotogrammi precedente per il thread.</span><span class="sxs-lookup"><span data-stu-id="2627d-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2627d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2627d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2627d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2627d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="2627d-106">out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di fotogrammi precedente per il thread.</span><span class="sxs-lookup"><span data-stu-id="2627d-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="2627d-107">Se questa catena è la prima catena, `ppChain` è null.</span><span class="sxs-lookup"><span data-stu-id="2627d-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2627d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2627d-108">Requirements</span></span>  
 <span data-ttu-id="2627d-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2627d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2627d-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2627d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2627d-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2627d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2627d-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2627d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
