---
title: Enumerazione CorDebugCodeInvokePurpose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInvokePurpose
api_location: mscordbi.dll
api_type: COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41938a11d7d92fd728772aa45bd8e97f137e5d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="46385-102">Enumerazione CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="46385-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="46385-103">Descrive il motivo per cui una funzione esportata chiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="46385-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46385-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46385-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="46385-105">Membri</span><span class="sxs-lookup"><span data-stu-id="46385-105">Members</span></span>  
  
|<span data-ttu-id="46385-106">Membro</span><span class="sxs-lookup"><span data-stu-id="46385-106">Member</span></span>|<span data-ttu-id="46385-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46385-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="46385-108">Nessuno o sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="46385-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="46385-109">Il codice gestito esegue qualsiasi punto di ingresso gestito, ad esempio p-invoke inverso.</span><span class="sxs-lookup"><span data-stu-id="46385-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="46385-110">Eventuali altri scopi più dettagliati non sono noti al runtime.</span><span class="sxs-lookup"><span data-stu-id="46385-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="46385-111">Il codice gestito esegue un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="46385-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="46385-112">Il codice gestito esegue l'implementazione per alcuni metodi dell'interfaccia chiamati.</span><span class="sxs-lookup"><span data-stu-id="46385-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46385-113">Note</span><span class="sxs-lookup"><span data-stu-id="46385-113">Remarks</span></span>  
 <span data-ttu-id="46385-114">Questa enumerazione viene utilizzata per la [Icordebugprocess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metodo per fornire informazioni sull'avanzamento tramite codice gestito.</span><span class="sxs-lookup"><span data-stu-id="46385-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46385-115">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="46385-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46385-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46385-116">Requirements</span></span>  
 <span data-ttu-id="46385-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46385-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46385-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="46385-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46385-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46385-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46385-120">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46385-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46385-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46385-121">See Also</span></span>  
 [<span data-ttu-id="46385-122">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="46385-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="46385-123">Debug</span><span class="sxs-lookup"><span data-stu-id="46385-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
