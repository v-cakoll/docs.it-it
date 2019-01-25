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
ms.openlocfilehash: dd1a622faa095836a3d5c22c7a18084482074c2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653216"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="79002-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="79002-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="79002-103">Indica il tipo di percorso nativo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="79002-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79002-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79002-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="79002-105">Membri</span><span class="sxs-lookup"><span data-stu-id="79002-105">Members</span></span>  
  
|<span data-ttu-id="79002-106">Membro</span><span class="sxs-lookup"><span data-stu-id="79002-106">Member</span></span>|<span data-ttu-id="79002-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79002-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="79002-108">La variabile è in un registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="79002-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="79002-109">La variabile è in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="79002-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="79002-110">La variabile non viene archiviata in un registro o una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="79002-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79002-111">Note</span><span class="sxs-lookup"><span data-stu-id="79002-111">Remarks</span></span>  
 <span data-ttu-id="79002-112">Un membro del `VariableLocationType` enumerazione viene restituita per la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="79002-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79002-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79002-113">Requirements</span></span>  
 <span data-ttu-id="79002-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79002-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79002-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79002-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79002-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79002-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79002-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79002-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79002-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79002-118">See also</span></span>
- [<span data-ttu-id="79002-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="79002-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
