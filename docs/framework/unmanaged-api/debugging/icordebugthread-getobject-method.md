---
title: Metodo ICorDebugThread::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
ms.openlocfilehash: 5cb95fb7cf70dbf7616e9bc59ebf44de090de883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133437"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="885ea-102">Metodo ICorDebugThread::GetObject</span><span class="sxs-lookup"><span data-stu-id="885ea-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="885ea-103">Ottiene un puntatore a interfaccia al thread di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="885ea-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="885ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="885ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="885ea-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="885ea-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugValue che rappresenta il thread CLR.</span><span class="sxs-lookup"><span data-stu-id="885ea-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885ea-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="885ea-107">Requirements</span></span>  
 <span data-ttu-id="885ea-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="885ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885ea-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="885ea-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="885ea-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885ea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885ea-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885ea-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="885ea-112">See also</span></span>

- <xref:System.Threading.Thread>
