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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf777214c015f0bbc434e3123d3ec7ef7f723549
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405652"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="c40cc-102">Enumerazione CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="c40cc-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="c40cc-103">Descrive in che modo una funzione esportata richiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c40cc-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c40cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c40cc-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="c40cc-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c40cc-105">Members</span></span>  
  
|<span data-ttu-id="c40cc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c40cc-106">Member</span></span>|<span data-ttu-id="c40cc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c40cc-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="c40cc-108">Se il codice gestito viene richiamato con questo metodo, in un secondo momento dovrà essere individuato mediante eventi espliciti o punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="c40cc-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="c40cc-109">--oppure--</span><span class="sxs-lookup"><span data-stu-id="c40cc-109">--or--</span></span><br /><br /> <span data-ttu-id="c40cc-110">È possibile che alcune parti di codice gestito chiamate dal metodo vadano perdute perché non esiste un modo semplice per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="c40cc-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="c40cc-111">--oppure--</span><span class="sxs-lookup"><span data-stu-id="c40cc-111">--or--</span></span><br /><br /> <span data-ttu-id="c40cc-112">Il metodo può non richiamare il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c40cc-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="c40cc-113">Il metodo richiama il codice gestito mediante un'istruzione di restituzione.</span><span class="sxs-lookup"><span data-stu-id="c40cc-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="c40cc-114">Nel codice gestito successivo viene eseguita l'uscita.</span><span class="sxs-lookup"><span data-stu-id="c40cc-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="c40cc-115">Questo metodo richiama il codice gestito mediante una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="c40cc-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="c40cc-116">L'esecuzione passo-passo e l'esecuzione di istruzioni per tutte le istruzioni della chiamata vengono completate nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c40cc-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c40cc-117">Note</span><span class="sxs-lookup"><span data-stu-id="c40cc-117">Remarks</span></span>  
 <span data-ttu-id="c40cc-118">Questa enumerazione viene utilizzata per la [Icordebugprocess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metodo per fornire informazioni sull'avanzamento tramite codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c40cc-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c40cc-119">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c40cc-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c40cc-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c40cc-120">Requirements</span></span>  
 <span data-ttu-id="c40cc-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c40cc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c40cc-122">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c40cc-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c40cc-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c40cc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c40cc-124">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c40cc-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40cc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c40cc-125">See Also</span></span>  
 [<span data-ttu-id="c40cc-126">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="c40cc-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="c40cc-127">Debug</span><span class="sxs-lookup"><span data-stu-id="c40cc-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
