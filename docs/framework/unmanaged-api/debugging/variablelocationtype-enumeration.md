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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790305"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="1d085-102">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="1d085-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="1d085-103">Indica il tipo di percorso nativo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="1d085-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d085-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d085-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="1d085-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1d085-105">Members</span></span>  
  
|<span data-ttu-id="1d085-106">Member</span><span class="sxs-lookup"><span data-stu-id="1d085-106">Member</span></span>|<span data-ttu-id="1d085-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d085-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="1d085-108">La variabile si trova in un registro.</span><span class="sxs-lookup"><span data-stu-id="1d085-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="1d085-109">La variabile si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="1d085-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="1d085-110">La variabile non è archiviata in un registro o in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="1d085-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d085-111">Note</span><span class="sxs-lookup"><span data-stu-id="1d085-111">Remarks</span></span>  
 <span data-ttu-id="1d085-112">Un membro dell'enumerazione `VariableLocationType` viene restituito dal metodo [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d085-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d085-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1d085-113">Requirements</span></span>  
 <span data-ttu-id="1d085-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d085-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d085-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d085-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d085-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d085-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d085-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d085-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d085-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d085-118">See also</span></span>

- [<span data-ttu-id="1d085-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="1d085-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
