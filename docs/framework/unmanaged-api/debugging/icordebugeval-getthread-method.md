---
title: Metodo ICorDebugEval::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: b985ada09e0e1914c5e60da61a45398fc6098b33
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976278"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="78177-102">Metodo ICorDebugEval::GetThread</span><span class="sxs-lookup"><span data-stu-id="78177-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="78177-103">Ottiene il thread in cui è in esecuzione la valutazione o verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="78177-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78177-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78177-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78177-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78177-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="78177-106">out Puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="78177-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78177-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78177-107">Requirements</span></span>  
 <span data-ttu-id="78177-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78177-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78177-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78177-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78177-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78177-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78177-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78177-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
