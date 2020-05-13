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
ms.openlocfilehash: 5fa3bafd35912a7729833896f7e6f0bb2ff9b121
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212386"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="26e99-102">Metodo ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="26e99-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="26e99-103">Notifica al debugger che un thread ha avviato l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="26e99-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26e99-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26e99-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26e99-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="26e99-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread.</span><span class="sxs-lookup"><span data-stu-id="26e99-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="26e99-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="26e99-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26e99-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="26e99-108">Remarks</span></span>  
 <span data-ttu-id="26e99-109">Il thread verrà posizionato in corrispondenza della prima istruzione di codice gestito da eseguire.</span><span class="sxs-lookup"><span data-stu-id="26e99-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e99-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26e99-110">Requirements</span></span>  
 <span data-ttu-id="26e99-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e99-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e99-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26e99-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26e99-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26e99-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26e99-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e99-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e99-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26e99-115">See also</span></span>

- [<span data-ttu-id="26e99-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="26e99-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
