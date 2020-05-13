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
ms.openlocfilehash: fa3cbfee0359b8477f9efe88fe72837b86611bf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212802"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="d32ab-102">Metodo ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="d32ab-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="d32ab-103">Imposta un valore che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.</span><span class="sxs-lookup"><span data-stu-id="d32ab-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d32ab-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d32ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d32ab-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="d32ab-106">in Costante [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.</span><span class="sxs-lookup"><span data-stu-id="d32ab-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d32ab-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d32ab-107">Remarks</span></span>  
 <span data-ttu-id="d32ab-108">Se il criterio è impostato correttamente, il metodo restituisce `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="d32ab-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="d32ab-109">Se non `ePolicy` è compreso nell'intervallo dei valori enumerati definiti da [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), il metodo restituisce `E_INVALIDARG` e la chiamata al metodo non ha effetto.</span><span class="sxs-lookup"><span data-stu-id="d32ab-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="d32ab-110">Se non è possibile aggiornare i criteri del generatore di immagini native (Ngen. exe), il metodo restituisce `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="d32ab-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="d32ab-111">Il `ICorDebugProcess5::EnableNGenPolicy` metodo può essere chiamato in qualsiasi momento durante il ciclo di vita del processo.</span><span class="sxs-lookup"><span data-stu-id="d32ab-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="d32ab-112">Il criterio è attivo per tutti i moduli caricati dopo l'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d32ab-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d32ab-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d32ab-113">Requirements</span></span>  
 <span data-ttu-id="d32ab-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d32ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d32ab-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d32ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d32ab-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d32ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d32ab-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d32ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32ab-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d32ab-118">See also</span></span>

- [<span data-ttu-id="d32ab-119">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="d32ab-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d32ab-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d32ab-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d32ab-121">Debug</span><span class="sxs-lookup"><span data-stu-id="d32ab-121">Debugging</span></span>](index.md)
