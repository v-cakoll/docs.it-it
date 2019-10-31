---
title: Metodo ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 33219d9a67379244e23da49c13617a4c4a2fa66d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133457"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="7f2be-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="7f2be-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="7f2be-103">Ottiene l'handle corrente per la parte attiva di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7f2be-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f2be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f2be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f2be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f2be-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="7f2be-106">out Puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="7f2be-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f2be-107">Note</span><span class="sxs-lookup"><span data-stu-id="7f2be-107">Remarks</span></span>  
 <span data-ttu-id="7f2be-108">L'handle può cambiare durante l'esecuzione del processo e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="7f2be-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="7f2be-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="7f2be-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="7f2be-110">Il debugger dovrebbe duplicarlo prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="7f2be-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f2be-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f2be-111">Requirements</span></span>  
 <span data-ttu-id="7f2be-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f2be-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f2be-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f2be-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f2be-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f2be-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f2be-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f2be-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
