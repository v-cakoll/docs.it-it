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
ms.openlocfilehash: ddb5af486ab6fb1c8c4fabf3ccf7b43d037e1eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789326"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="12eb1-102">Enumerazione CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="12eb1-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="12eb1-103">Indica se un intervallo specifico di istruzioni native, rappresentato da un'istanza della struttura COR_DEBUG_IL_TO_NATIVE_MAP, corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="12eb1-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12eb1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12eb1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="12eb1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="12eb1-105">Members</span></span>  
  
|<span data-ttu-id="12eb1-106">Member</span><span class="sxs-lookup"><span data-stu-id="12eb1-106">Member</span></span>|<span data-ttu-id="12eb1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12eb1-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="12eb1-108">L'intervallo di istruzioni native non corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="12eb1-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="12eb1-109">L'intervallo di istruzioni native corrisponde al prologo.</span><span class="sxs-lookup"><span data-stu-id="12eb1-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="12eb1-110">L'intervallo di istruzioni native corrisponde all'epilogo.</span><span class="sxs-lookup"><span data-stu-id="12eb1-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12eb1-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="12eb1-111">Requirements</span></span>  
 <span data-ttu-id="12eb1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12eb1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12eb1-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12eb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12eb1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12eb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12eb1-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12eb1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12eb1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12eb1-116">See also</span></span>

- [<span data-ttu-id="12eb1-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="12eb1-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="12eb1-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="12eb1-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
