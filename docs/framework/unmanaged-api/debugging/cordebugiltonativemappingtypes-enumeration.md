---
title: Enumerazione CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: 949d04fe8d9ce492fb320fb4732677ffb35302ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132822"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="94a0e-102">Enumerazione CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="94a0e-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="94a0e-103">Indica se un intervallo specifico di istruzioni native, rappresentato da un'istanza della struttura COR_DEBUG_IL_TO_NATIVE_MAP, corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="94a0e-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a0e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94a0e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="94a0e-105">Members</span><span class="sxs-lookup"><span data-stu-id="94a0e-105">Members</span></span>  
  
|<span data-ttu-id="94a0e-106">Member</span><span class="sxs-lookup"><span data-stu-id="94a0e-106">Member</span></span>|<span data-ttu-id="94a0e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94a0e-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="94a0e-108">L'intervallo di istruzioni native non corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="94a0e-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="94a0e-109">L'intervallo di istruzioni native corrisponde al prologo.</span><span class="sxs-lookup"><span data-stu-id="94a0e-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="94a0e-110">L'intervallo di istruzioni native corrisponde all'epilogo.</span><span class="sxs-lookup"><span data-stu-id="94a0e-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94a0e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94a0e-111">Requirements</span></span>  
 <span data-ttu-id="94a0e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a0e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a0e-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a0e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a0e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a0e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a0e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a0e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a0e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94a0e-116">See also</span></span>

- [<span data-ttu-id="94a0e-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="94a0e-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="94a0e-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="94a0e-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
