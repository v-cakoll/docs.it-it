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
ms.openlocfilehash: 1cc7a299e6be328095c0368acf0a4b767fb74d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423949"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="ea393-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="ea393-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="ea393-103">Indica il tipo nativo di percorso di una variabile.</span><span class="sxs-lookup"><span data-stu-id="ea393-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea393-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea393-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="ea393-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ea393-105">Members</span></span>  
  
|<span data-ttu-id="ea393-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ea393-106">Member</span></span>|<span data-ttu-id="ea393-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea393-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="ea393-108">La variabile è in un registro.</span><span class="sxs-lookup"><span data-stu-id="ea393-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="ea393-109">La variabile è in una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="ea393-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="ea393-110">La variabile non viene archiviata in un registro o di una posizione di memoria relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="ea393-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea393-111">Note</span><span class="sxs-lookup"><span data-stu-id="ea393-111">Remarks</span></span>  
 <span data-ttu-id="ea393-112">Un membro del `VariableLocationType` enumerazione restituito dal [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="ea393-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea393-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea393-113">Requirements</span></span>  
 <span data-ttu-id="ea393-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea393-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea393-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ea393-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea393-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ea393-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea393-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea393-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea393-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea393-118">See Also</span></span>  
 [<span data-ttu-id="ea393-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ea393-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
