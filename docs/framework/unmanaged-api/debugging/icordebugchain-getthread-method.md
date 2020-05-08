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
ms.openlocfilehash: 28b54026c8743f31a420e164944f60709e2e271b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894361"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="73ca1-102">Metodo ICorDebugChain::GetThread</span><span class="sxs-lookup"><span data-stu-id="73ca1-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="73ca1-103">Ottiene il thread fisico di cui fa parte questa catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="73ca1-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ca1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73ca1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73ca1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73ca1-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="73ca1-106">out Puntatore a un oggetto ICorDebugThread che rappresenta il thread fisico di cui fa parte questa catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="73ca1-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73ca1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73ca1-107">Requirements</span></span>  
 <span data-ttu-id="73ca1-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73ca1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73ca1-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73ca1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73ca1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73ca1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73ca1-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73ca1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
