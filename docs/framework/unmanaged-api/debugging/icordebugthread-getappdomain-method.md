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
ms.openlocfilehash: 52efebf8a2786afaabe87b96b35a13c5fa1eb578
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379786"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="651b1-102">Metodo ICorDebugThread::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="651b1-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="651b1-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui è attualmente in esecuzione il ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="651b1-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="651b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="651b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="651b1-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="651b1-106">out Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è attualmente in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="651b1-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="651b1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="651b1-107">Requirements</span></span>  
 <span data-ttu-id="651b1-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="651b1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="651b1-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="651b1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="651b1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="651b1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="651b1-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="651b1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
