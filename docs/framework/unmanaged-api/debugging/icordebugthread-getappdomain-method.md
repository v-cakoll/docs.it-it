---
title: Metodo ICorDebugThread::GetAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
ms.openlocfilehash: a845eed993914e02de34ec5c60ed232ccabc561e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133521"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="13e67-102">Metodo ICorDebugThread::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="13e67-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="13e67-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui è attualmente in esecuzione il ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="13e67-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13e67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13e67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13e67-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="13e67-106">out Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è attualmente in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="13e67-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e67-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13e67-107">Requirements</span></span>  
 <span data-ttu-id="13e67-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13e67-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e67-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e67-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e67-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e67-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13e67-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e67-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
