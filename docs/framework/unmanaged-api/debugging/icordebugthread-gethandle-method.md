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
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379744"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="1b8c8-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="1b8c8-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="1b8c8-103">Ottiene l'handle corrente per la parte attiva di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="1b8c8-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b8c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b8c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b8c8-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="1b8c8-106">out Puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="1b8c8-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b8c8-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1b8c8-107">Remarks</span></span>  
 <span data-ttu-id="1b8c8-108">L'handle può cambiare durante l'esecuzione del processo e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="1b8c8-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="1b8c8-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="1b8c8-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="1b8c8-110">Il debugger dovrebbe duplicarlo prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="1b8c8-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b8c8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b8c8-111">Requirements</span></span>  
 <span data-ttu-id="1b8c8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b8c8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b8c8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b8c8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b8c8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b8c8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b8c8-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
