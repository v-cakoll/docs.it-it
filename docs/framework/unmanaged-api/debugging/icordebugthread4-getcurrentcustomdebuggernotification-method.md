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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378703"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="3b97f-102">Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="3b97f-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="3b97f-103">Ottiene l'oggetto [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) corrente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3b97f-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b97f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b97f-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="3b97f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b97f-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="3b97f-106">out Puntatore all' `ICorDebugManagedCallback3::CustomNotification` oggetto corrente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3b97f-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b97f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3b97f-107">Remarks</span></span>

<span data-ttu-id="3b97f-108">Il valore di `ppNotificationObject` è null se il metodo non viene chiamato dall'interno di un `ICorDebugManagedCallback3::CustomNotification` callback o se non esiste alcun oggetto notifica corrente.</span><span class="sxs-lookup"><span data-stu-id="3b97f-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b97f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b97f-109">Requirements</span></span>

<span data-ttu-id="3b97f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b97f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3b97f-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b97f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3b97f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b97f-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3b97f-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b97f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3b97f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b97f-114">See also</span></span>

- [<span data-ttu-id="3b97f-115">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3b97f-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="3b97f-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3b97f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3b97f-117">Debug</span><span class="sxs-lookup"><span data-stu-id="3b97f-117">Debugging</span></span>](index.md)
