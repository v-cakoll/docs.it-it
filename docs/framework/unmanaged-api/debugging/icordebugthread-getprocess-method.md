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
ms.openlocfilehash: 76dfc10b9d9069f6d53cd292f241ae3080c6443a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379801"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="95784-102">Metodo ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="95784-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="95784-103">Ottiene un puntatore a interfaccia al processo di cui questo oggetto ICorDebugThread fa parte.</span><span class="sxs-lookup"><span data-stu-id="95784-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95784-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95784-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95784-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95784-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="95784-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="95784-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95784-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95784-107">Requirements</span></span>  
 <span data-ttu-id="95784-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95784-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95784-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95784-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95784-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95784-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95784-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95784-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
