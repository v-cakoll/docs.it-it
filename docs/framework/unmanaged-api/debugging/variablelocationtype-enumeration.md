---
title: Enumerazione VariableLocationType
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2093466c78b039a06a01e2d850b88ff4543d0ab3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752465"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="e28c9-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="e28c9-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="e28c9-103">Indica il tipo di percorso nativo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="e28c9-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e28c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e28c9-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="e28c9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e28c9-105">Members</span></span>  
  
|<span data-ttu-id="e28c9-106">Member</span><span class="sxs-lookup"><span data-stu-id="e28c9-106">Member</span></span>|<span data-ttu-id="e28c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e28c9-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="e28c9-108">La variabile è in un registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e28c9-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="e28c9-109">La variabile è in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="e28c9-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="e28c9-110">La variabile non viene archiviata in un registro o una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="e28c9-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e28c9-111">Note</span><span class="sxs-lookup"><span data-stu-id="e28c9-111">Remarks</span></span>  
 <span data-ttu-id="e28c9-112">Un membro del `VariableLocationType` enumerazione viene restituita per la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e28c9-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e28c9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e28c9-113">Requirements</span></span>  
 <span data-ttu-id="e28c9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e28c9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28c9-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e28c9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e28c9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e28c9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e28c9-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28c9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e28c9-118">See also</span></span>

- [<span data-ttu-id="e28c9-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="e28c9-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
