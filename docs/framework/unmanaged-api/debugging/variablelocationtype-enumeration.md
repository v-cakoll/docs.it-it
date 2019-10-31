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
ms.openlocfilehash: 861d5daa481132d3d6527e8d5fbccfab6436c5fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139109"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="3b857-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="3b857-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="3b857-103">Indica il tipo di percorso nativo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="3b857-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b857-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b857-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="3b857-105">Members</span><span class="sxs-lookup"><span data-stu-id="3b857-105">Members</span></span>  
  
|<span data-ttu-id="3b857-106">Member</span><span class="sxs-lookup"><span data-stu-id="3b857-106">Member</span></span>|<span data-ttu-id="3b857-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b857-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="3b857-108">La variabile si trova in un registro.</span><span class="sxs-lookup"><span data-stu-id="3b857-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="3b857-109">La variabile si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="3b857-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="3b857-110">La variabile non è archiviata in un registro o in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="3b857-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b857-111">Note</span><span class="sxs-lookup"><span data-stu-id="3b857-111">Remarks</span></span>  
 <span data-ttu-id="3b857-112">Un membro dell'enumerazione `VariableLocationType` viene restituito dal metodo [ICorDebugVariableHome:: GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b857-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b857-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b857-113">Requirements</span></span>  
 <span data-ttu-id="3b857-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b857-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b857-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b857-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b857-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b857-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b857-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b857-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b857-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b857-118">See also</span></span>

- [<span data-ttu-id="3b857-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3b857-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
