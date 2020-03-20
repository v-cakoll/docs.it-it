---
title: Enumerazione CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: 54332f5b3383f1c1513242a79cbd81eb8aa5c4f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179256"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="e9fa2-102">Enumerazione CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="e9fa2-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="e9fa2-103">Descrive in che modo una funzione esportata richiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9fa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9fa2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="e9fa2-105">Members</span><span class="sxs-lookup"><span data-stu-id="e9fa2-105">Members</span></span>  
  
|<span data-ttu-id="e9fa2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e9fa2-106">Member</span></span>|<span data-ttu-id="e9fa2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fa2-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="e9fa2-108">Se il codice gestito viene richiamato con questo metodo, in un secondo momento dovrà essere individuato mediante eventi espliciti o punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="e9fa2-109">--oppure--</span><span class="sxs-lookup"><span data-stu-id="e9fa2-109">--or--</span></span><br /><br /> <span data-ttu-id="e9fa2-110">È possibile che alcune parti di codice gestito chiamate dal metodo vadano perdute perché non esiste un modo semplice per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="e9fa2-111">--oppure--</span><span class="sxs-lookup"><span data-stu-id="e9fa2-111">--or--</span></span><br /><br /> <span data-ttu-id="e9fa2-112">Il metodo può non richiamare il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="e9fa2-113">Il metodo richiama il codice gestito mediante un'istruzione di restituzione.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="e9fa2-114">Nel codice gestito successivo viene eseguita l'uscita.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="e9fa2-115">Questo metodo richiama il codice gestito mediante una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="e9fa2-116">L'esecuzione passo-passo e l'esecuzione di istruzioni per tutte le istruzioni della chiamata vengono completate nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9fa2-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e9fa2-117">Remarks</span></span>  
 <span data-ttu-id="e9fa2-118">Questa enumerazione viene utilizzata dal [metodo ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) per fornire informazioni sull'esecuzione di istruzioni nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9fa2-119">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e9fa2-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9fa2-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9fa2-120">Requirements</span></span>  
 <span data-ttu-id="e9fa2-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9fa2-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9fa2-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9fa2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9fa2-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9fa2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9fa2-124">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9fa2-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9fa2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9fa2-125">See also</span></span>

- [<span data-ttu-id="e9fa2-126">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="e9fa2-126">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="e9fa2-127">Debug</span><span class="sxs-lookup"><span data-stu-id="e9fa2-127">Debugging</span></span>](index.md)
