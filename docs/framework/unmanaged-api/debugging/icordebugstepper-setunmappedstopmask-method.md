---
title: Metodo ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474956"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="ff629-102">Metodo ICorDebugStepper::SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="ff629-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="ff629-103">Imposta un valore che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ff629-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff629-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff629-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff629-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff629-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="ff629-106">[in] Valore dell'enumerazione CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui il debugger si arresta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ff629-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="ff629-107">Il valore predefinito è STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="ff629-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="ff629-108">Il valore STOP_UNMANAGED è valido solo con il debug di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="ff629-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff629-109">Note</span><span class="sxs-lookup"><span data-stu-id="ff629-109">Remarks</span></span>  
 <span data-ttu-id="ff629-110">Quando il debugger rileva una compilazione just-in-time (JIT) non ha alcun mapping corrispondente in Microsoft intermediate language (MSIL), arresterà l'esecuzione se è stato impostato il flag che specifica tale tipo di codice non mappato; in caso contrario, l'esecuzione di istruzioni in modo trasparente continua.</span><span class="sxs-lookup"><span data-stu-id="ff629-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="ff629-111">Se il debugger non usa un gestore di istruzioni per immettere un metodo, quindi non sarà necessariamente Esegui istruzione/routine codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="ff629-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff629-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff629-112">Requirements</span></span>  
 <span data-ttu-id="ff629-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff629-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff629-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff629-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff629-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff629-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff629-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff629-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
