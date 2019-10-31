---
title: Metodo ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133544"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="73d7c-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="73d7c-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="73d7c-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="73d7c-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73d7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73d7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73d7c-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="73d7c-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="73d7c-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73d7c-107">Note</span><span class="sxs-lookup"><span data-stu-id="73d7c-107">Remarks</span></span>  
 <span data-ttu-id="73d7c-108">Il parametro `ppFrame` è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="73d7c-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d7c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73d7c-109">Requirements</span></span>  
 <span data-ttu-id="73d7c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73d7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73d7c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73d7c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73d7c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73d7c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73d7c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73d7c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
