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
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212126"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="f5723-102">Metodo ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="f5723-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="f5723-103">Abilita e Disabilita le notifiche personalizzate del debugger del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f5723-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5723-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5723-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5723-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5723-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f5723-106">in Tipo che specifica le notifiche personalizzate del debugger.</span><span class="sxs-lookup"><span data-stu-id="f5723-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="f5723-107">[in] `true` per abilitare le notifiche personalizzate del debugger; `false`per disabilitare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="f5723-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="f5723-108">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f5723-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5723-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f5723-109">Remarks</span></span>  
 <span data-ttu-id="f5723-110">Quando `fEnable` è impostato su `true` , le chiamate al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Metodo attivano un callback [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5723-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="f5723-111">Le notifiche sono disabilitate per impostazione predefinita. Pertanto, è necessario che il debugger specifichi i tipi di notifica che conosce e desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f5723-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="f5723-112">Poiché l'ambito della classe [ICorDebugClass](icordebug-interface.md) è definito dal dominio dell'applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione nel processo se desidera ricevere la notifica nell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="f5723-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="f5723-113">A partire da .NET Framework 4, l'unica notifica supportata è una notifica di dipendenza tra thread.</span><span class="sxs-lookup"><span data-stu-id="f5723-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5723-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5723-114">Requirements</span></span>  
 <span data-ttu-id="f5723-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5723-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5723-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5723-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5723-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5723-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5723-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5723-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5723-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5723-119">See also</span></span>

- [<span data-ttu-id="f5723-120">Interfaccia ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="f5723-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="f5723-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f5723-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f5723-122">Debug</span><span class="sxs-lookup"><span data-stu-id="f5723-122">Debugging</span></span>](index.md)
