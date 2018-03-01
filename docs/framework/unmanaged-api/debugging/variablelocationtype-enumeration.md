---
title: Enumerazione VariableLocationType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ea476ef32b807823108aa2836778da576618214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="94adc-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="94adc-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="94adc-103">Indica il tipo nativo di percorso di una variabile.</span><span class="sxs-lookup"><span data-stu-id="94adc-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94adc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94adc-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="94adc-105">Membri</span><span class="sxs-lookup"><span data-stu-id="94adc-105">Members</span></span>  
  
|<span data-ttu-id="94adc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="94adc-106">Member</span></span>|<span data-ttu-id="94adc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94adc-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="94adc-108">La variabile è in un registro.</span><span class="sxs-lookup"><span data-stu-id="94adc-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="94adc-109">La variabile è in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="94adc-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="94adc-110">La variabile non viene archiviata in un registro o di una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="94adc-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94adc-111">Note</span><span class="sxs-lookup"><span data-stu-id="94adc-111">Remarks</span></span>  
 <span data-ttu-id="94adc-112">Un membro del `VariableLocationType` enumerazione restituito dal [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="94adc-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94adc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94adc-113">Requirements</span></span>  
 <span data-ttu-id="94adc-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94adc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94adc-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="94adc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94adc-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94adc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94adc-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94adc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94adc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94adc-118">See Also</span></span>  
 [<span data-ttu-id="94adc-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="94adc-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
