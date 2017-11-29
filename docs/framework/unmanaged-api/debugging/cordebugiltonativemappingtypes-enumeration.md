---
title: Enumerazione CorDebugIlToNativeMappingTypes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIlToNativeMappingTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIlToNativeMappingTypes
helpviewer_keywords: CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03046ebb678df64ad3d151aaadba313645417979
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="731b2-102">Enumerazione CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="731b2-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="731b2-103">Indica se un determinato intervallo di istruzioni native, rappresentato da un'istanza della struttura COR_DEBUG_IL_TO_NATIVE_MAP, corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="731b2-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="731b2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="731b2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="731b2-105">Members</span></span>  
  
|<span data-ttu-id="731b2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="731b2-106">Member</span></span>|<span data-ttu-id="731b2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="731b2-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="731b2-108">L'intervallo di istruzioni native non corrisponde a qualsiasi area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="731b2-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="731b2-109">L'intervallo di istruzioni native corrisponde al prologo.</span><span class="sxs-lookup"><span data-stu-id="731b2-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="731b2-110">L'intervallo di istruzioni native corrisponde all'epilogo.</span><span class="sxs-lookup"><span data-stu-id="731b2-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="731b2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="731b2-111">Requirements</span></span>  
 <span data-ttu-id="731b2-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="731b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="731b2-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="731b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="731b2-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="731b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="731b2-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="731b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731b2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="731b2-116">See Also</span></span>  
 [<span data-ttu-id="731b2-117">GetILToNativeMapping (metodo)</span><span class="sxs-lookup"><span data-stu-id="731b2-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="731b2-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="731b2-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
