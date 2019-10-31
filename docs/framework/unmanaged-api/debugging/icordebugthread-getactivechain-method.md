---
title: Metodo ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: 99a617ef21ee3c3319b1ebe7d3ab8367659b6ef8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133547"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="1a1b2-102">Metodo ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="1a1b2-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="1a1b2-103">Ottiene un puntatore di interfaccia alla catena di stack attiva (più recente) in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="1a1b2-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a1b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a1b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a1b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a1b2-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="1a1b2-106">out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di stack.</span><span class="sxs-lookup"><span data-stu-id="1a1b2-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a1b2-107">Note</span><span class="sxs-lookup"><span data-stu-id="1a1b2-107">Remarks</span></span>  
 <span data-ttu-id="1a1b2-108">Il parametro `ppChain` è null se non è attualmente attiva alcuna catena di stack.</span><span class="sxs-lookup"><span data-stu-id="1a1b2-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a1b2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a1b2-109">Requirements</span></span>  
 <span data-ttu-id="1a1b2-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a1b2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a1b2-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a1b2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a1b2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a1b2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a1b2-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a1b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
