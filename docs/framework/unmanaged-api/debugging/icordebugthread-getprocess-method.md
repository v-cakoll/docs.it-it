---
title: Metodo ICorDebugThread::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: 8928e22b70af0360660c30289ee999a3e4c5e99e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133480"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="3b87b-102">Metodo ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="3b87b-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="3b87b-103">Ottiene un puntatore a interfaccia al processo di cui questo oggetto ICorDebugThread fa parte.</span><span class="sxs-lookup"><span data-stu-id="3b87b-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b87b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b87b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b87b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b87b-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3b87b-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="3b87b-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b87b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b87b-107">Requirements</span></span>  
 <span data-ttu-id="3b87b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b87b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b87b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b87b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b87b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b87b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b87b-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b87b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
