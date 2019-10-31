---
title: Metodo ICorDebugManagedCallback::CreateThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
ms.openlocfilehash: 401cb41d8231e78b8657513e1a755a50814e463b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137399"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="d60e0-102">Metodo ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="d60e0-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="d60e0-103">Notifica al debugger che un thread ha avviato l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d60e0-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d60e0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d60e0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d60e0-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread.</span><span class="sxs-lookup"><span data-stu-id="d60e0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="d60e0-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="d60e0-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d60e0-108">Note</span><span class="sxs-lookup"><span data-stu-id="d60e0-108">Remarks</span></span>  
 <span data-ttu-id="d60e0-109">Il thread verrà posizionato in corrispondenza della prima istruzione di codice gestito da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d60e0-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60e0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d60e0-110">Requirements</span></span>  
 <span data-ttu-id="d60e0-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d60e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60e0-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d60e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d60e0-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d60e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d60e0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d60e0-115">See also</span></span>

- [<span data-ttu-id="d60e0-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d60e0-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
