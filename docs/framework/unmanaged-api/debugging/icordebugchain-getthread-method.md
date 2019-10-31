---
title: Metodo ICorDebugChain::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: b964d58bddb174da38fc8988ec807fd3129b5fcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123818"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="f20ce-102">Metodo ICorDebugChain::GetThread</span><span class="sxs-lookup"><span data-stu-id="f20ce-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="f20ce-103">Ottiene il thread fisico di cui fa parte questa catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="f20ce-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f20ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f20ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f20ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f20ce-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="f20ce-106">out Puntatore a un oggetto ICorDebugThread che rappresenta il thread fisico di cui fa parte questa catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="f20ce-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f20ce-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f20ce-107">Requirements</span></span>  
 <span data-ttu-id="f20ce-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f20ce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f20ce-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f20ce-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f20ce-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f20ce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f20ce-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f20ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
