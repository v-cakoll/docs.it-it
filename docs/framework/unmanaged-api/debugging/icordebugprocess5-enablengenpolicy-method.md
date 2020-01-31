---
title: Metodo ICorDebugProcess5::EnableNGENPolicy
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792456"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="69cb7-102">Metodo ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="69cb7-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="69cb7-103">Imposta un valore che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.</span><span class="sxs-lookup"><span data-stu-id="69cb7-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cb7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69cb7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69cb7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69cb7-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="69cb7-106">in Costante [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.</span><span class="sxs-lookup"><span data-stu-id="69cb7-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69cb7-107">Note</span><span class="sxs-lookup"><span data-stu-id="69cb7-107">Remarks</span></span>  
 <span data-ttu-id="69cb7-108">Se il criterio è impostato correttamente, il metodo restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="69cb7-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="69cb7-109">Se `ePolicy` non è compreso nell'intervallo dei valori enumerati definiti da [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), il metodo restituisce `E_INVALIDARG` e la chiamata al metodo non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="69cb7-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="69cb7-110">Se non è possibile aggiornare i criteri del generatore di immagini native (Ngen. exe), il metodo restituisce `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="69cb7-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="69cb7-111">Il metodo `ICorDebugProcess5::EnableNGenPolicy` può essere chiamato in qualsiasi momento durante il ciclo di vita del processo.</span><span class="sxs-lookup"><span data-stu-id="69cb7-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="69cb7-112">Il criterio è attivo per tutti i moduli caricati dopo l'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="69cb7-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cb7-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="69cb7-113">Requirements</span></span>  
 <span data-ttu-id="69cb7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69cb7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69cb7-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69cb7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69cb7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69cb7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69cb7-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69cb7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cb7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69cb7-118">See also</span></span>

- [<span data-ttu-id="69cb7-119">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="69cb7-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="69cb7-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="69cb7-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="69cb7-121">Debug</span><span class="sxs-lookup"><span data-stu-id="69cb7-121">Debugging</span></span>](index.md)
