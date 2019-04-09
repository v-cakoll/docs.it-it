---
title: Metodo ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8c8725bf21aefa3abf5fc41366d8f983bd686b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175747"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="30e25-102">Metodo ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="30e25-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="30e25-103">Abilita e disabilita le notifiche di debugger personalizzati del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="30e25-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30e25-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30e25-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30e25-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="30e25-106">[in] Tipo che specifica le notifiche di debugger personalizzati.</span><span class="sxs-lookup"><span data-stu-id="30e25-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="30e25-107">[in] `true` per abilitare le notifiche di debugger personalizzati. `false` per disabilitare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="30e25-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="30e25-108">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="30e25-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30e25-109">Note</span><span class="sxs-lookup"><span data-stu-id="30e25-109">Remarks</span></span>  
 <span data-ttu-id="30e25-110">Quando `fEnable` è impostata su `true`, le chiamate al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> trigger metodo un' [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="30e25-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="30e25-111">Le notifiche sono disabilitate per impostazione predefinita. Pertanto, il debugger deve specificare qualsiasi tipo di notifica a conoscenza e si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="30e25-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="30e25-112">Poiché il [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) classe ha come ambita dal dominio applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione del processo se vuole ricevere la notifica nell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="30e25-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="30e25-113">A partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], la sola notifica supportata da una notifica di dipendenza cross-thread.</span><span class="sxs-lookup"><span data-stu-id="30e25-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e25-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30e25-114">Requirements</span></span>  
 <span data-ttu-id="30e25-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e25-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e25-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30e25-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30e25-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e25-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="30e25-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="30e25-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30e25-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30e25-119">See also</span></span>

- [<span data-ttu-id="30e25-120">Interfaccia ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="30e25-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="30e25-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30e25-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="30e25-122">Debug</span><span class="sxs-lookup"><span data-stu-id="30e25-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
