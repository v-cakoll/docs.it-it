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
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178353"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="b95c6-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="b95c6-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="b95c6-103">Indica il tipo di posizione nativo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="b95c6-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b95c6-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="b95c6-105">Members</span><span class="sxs-lookup"><span data-stu-id="b95c6-105">Members</span></span>  
  
|<span data-ttu-id="b95c6-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b95c6-106">Member</span></span>|<span data-ttu-id="b95c6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b95c6-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="b95c6-108">La variabile si trova in un registro.</span><span class="sxs-lookup"><span data-stu-id="b95c6-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="b95c6-109">La variabile si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="b95c6-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="b95c6-110">La variabile non viene archiviata in un registro o in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="b95c6-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b95c6-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b95c6-111">Remarks</span></span>  
 <span data-ttu-id="b95c6-112">Un membro `VariableLocationType` dell'enumerazione viene restituito dal [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="b95c6-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b95c6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b95c6-113">Requirements</span></span>  
 <span data-ttu-id="b95c6-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b95c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b95c6-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b95c6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b95c6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b95c6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b95c6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b95c6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b95c6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b95c6-118">See also</span></span>

- [<span data-ttu-id="b95c6-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b95c6-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
