---
title: Metodo ICorDebugMDA::GetOSThreadId
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: c7ab77e9316023a97d2eafe8bcccc2b45e240cd0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207829"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="63771-102">Metodo ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="63771-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="63771-103">Ottiene l'identificatore del thread del sistema operativo su cui è in esecuzione l'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="63771-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63771-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63771-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63771-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63771-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="63771-106">out Puntatore all'identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="63771-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63771-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63771-107">Remarks</span></span>  
 <span data-ttu-id="63771-108">Il thread del sistema operativo viene usato al posto di ICorDebugThread per consentire situazioni in cui un assistente al debug gestito viene attivato in un thread nativo o in un thread gestito che non ha ancora immesso codice gestito.</span><span class="sxs-lookup"><span data-stu-id="63771-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63771-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63771-109">Requirements</span></span>  
 <span data-ttu-id="63771-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63771-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63771-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63771-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63771-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63771-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63771-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63771-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63771-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63771-114">See also</span></span>

- [<span data-ttu-id="63771-115">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="63771-115">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="63771-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="63771-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
