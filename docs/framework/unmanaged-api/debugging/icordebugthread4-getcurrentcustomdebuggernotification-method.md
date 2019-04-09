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
ms.openlocfilehash: f626ff6e562bd9bc94440f31e9470a45cc32cfbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216327"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="adb1d-102">Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="adb1d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="adb1d-103">Ottiene l'oggetto corrente [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="adb1d-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="adb1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adb1d-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="adb1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="adb1d-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="adb1d-106">[out] Un puntatore all'oggetto corrente `ICorDebugManagedCallback3::CustomNotification` oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="adb1d-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="adb1d-107">Note</span><span class="sxs-lookup"><span data-stu-id="adb1d-107">Remarks</span></span>

<span data-ttu-id="adb1d-108">Il valore di `ppNotificationObject` è null se il metodo non viene chiamato dall'interno una `ICorDebugManagedCallback3::CustomNotification` callback, o se non esiste alcun oggetto di notifica corrente.</span><span class="sxs-lookup"><span data-stu-id="adb1d-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="adb1d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="adb1d-109">Requirements</span></span>

<span data-ttu-id="adb1d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adb1d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="adb1d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adb1d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="adb1d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adb1d-112">**Library:** CorGuids.lib</span></span>

**<span data-ttu-id="adb1d-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="adb1d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a><span data-ttu-id="adb1d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adb1d-114">See also</span></span>

- [<span data-ttu-id="adb1d-115">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="adb1d-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="adb1d-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="adb1d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="adb1d-117">Debug</span><span class="sxs-lookup"><span data-stu-id="adb1d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
