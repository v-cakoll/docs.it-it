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
ms.openlocfilehash: 70e79378ad8eb2599199a1f7bc57cf530c9b4dd3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379687"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="58123-102">Metodo ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="58123-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="58123-103">Ottiene un puntatore di interfaccia alla catena di stack attiva (più recente) in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="58123-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58123-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58123-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58123-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58123-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="58123-106">out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di stack.</span><span class="sxs-lookup"><span data-stu-id="58123-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58123-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58123-107">Remarks</span></span>  
 <span data-ttu-id="58123-108">Il `ppChain` parametro è null se non è attualmente attiva alcuna catena di stack.</span><span class="sxs-lookup"><span data-stu-id="58123-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58123-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58123-109">Requirements</span></span>  
 <span data-ttu-id="58123-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58123-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58123-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58123-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58123-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58123-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58123-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58123-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
