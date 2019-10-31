---
title: Metodo ICorDebugChain::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: d6ee36ac4d4510637e5f8240c3b8930a9bec7970
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123839"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="dcace-102">Metodo ICorDebugChain::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="dcace-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="dcace-103">Ottiene il set di registri per la parte attiva della catena.</span><span class="sxs-lookup"><span data-stu-id="dcace-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcace-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcace-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcace-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcace-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="dcace-106">out Puntatore all'indirizzo di un oggetto [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) che rappresenta il set di registri per la parte attiva della catena.</span><span class="sxs-lookup"><span data-stu-id="dcace-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcace-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcace-107">Requirements</span></span>  
 <span data-ttu-id="dcace-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcace-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcace-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcace-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcace-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcace-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcace-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcace-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
