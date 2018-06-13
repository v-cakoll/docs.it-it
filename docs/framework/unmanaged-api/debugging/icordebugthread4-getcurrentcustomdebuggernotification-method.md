---
title: Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0529dee17469018e872951740a5899ef8664300a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421002"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="cca90-102">Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="cca90-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>
<span data-ttu-id="cca90-103">Ottiene l'oggetto corrente [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="cca90-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cca90-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cca90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cca90-105">Parameters</span></span>  
 `ppNOtificationObject`  
 <span data-ttu-id="cca90-106">[out] Un puntatore all'oggetto corrente `ICorDebugManagedCallback3::CustomNotification` oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="cca90-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cca90-107">Note</span><span class="sxs-lookup"><span data-stu-id="cca90-107">Remarks</span></span>  
 <span data-ttu-id="cca90-108">Il valore di `ppNotificationObject` è null se non viene chiamato il metodo dall'interno un `ICorDebugManagedCallback3::CustomNotification` callback, o se non esiste alcun oggetto di notifica corrente.</span><span class="sxs-lookup"><span data-stu-id="cca90-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cca90-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cca90-109">Requirements</span></span>  
 <span data-ttu-id="cca90-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cca90-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cca90-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cca90-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cca90-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cca90-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cca90-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cca90-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca90-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cca90-114">See Also</span></span>  
 [<span data-ttu-id="cca90-115">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="cca90-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="cca90-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cca90-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cca90-117">Debug</span><span class="sxs-lookup"><span data-stu-id="cca90-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
