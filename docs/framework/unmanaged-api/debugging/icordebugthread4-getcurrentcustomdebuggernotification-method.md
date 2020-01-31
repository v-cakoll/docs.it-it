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
ms.openlocfilehash: a8a377074ca1005ad8089dfd8e2a6a464bb86f60
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791363"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="a4a5d-102">Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="a4a5d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="a4a5d-103">Ottiene l'oggetto [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) corrente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a4a5d-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4a5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4a5d-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="a4a5d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4a5d-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="a4a5d-106">out Puntatore all'oggetto `ICorDebugManagedCallback3::CustomNotification` corrente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a4a5d-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4a5d-107">Note</span><span class="sxs-lookup"><span data-stu-id="a4a5d-107">Remarks</span></span>

<span data-ttu-id="a4a5d-108">Il valore di `ppNotificationObject` è null se il metodo non viene chiamato dall'interno di un callback `ICorDebugManagedCallback3::CustomNotification` o se non esiste alcun oggetto notifica corrente.</span><span class="sxs-lookup"><span data-stu-id="a4a5d-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4a5d-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a4a5d-109">Requirements</span></span>

<span data-ttu-id="a4a5d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a4a5d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4a5d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="a4a5d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4a5d-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a4a5d-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a5d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a4a5d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4a5d-114">See also</span></span>

- [<span data-ttu-id="a4a5d-115">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="a4a5d-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="a4a5d-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a4a5d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a4a5d-117">Debug</span><span class="sxs-lookup"><span data-stu-id="a4a5d-117">Debugging</span></span>](index.md)
