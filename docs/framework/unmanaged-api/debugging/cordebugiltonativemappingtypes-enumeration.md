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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f62707fb1e52a96cf3f131e9c11fee82ab03f4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097187"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="dd843-102">Enumerazione CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="dd843-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="dd843-103">Indica se un intervallo specifico di istruzioni native, rappresentata da un'istanza della struttura COR_DEBUG_IL_TO_NATIVE_MAP, corrisponde a un'area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="dd843-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd843-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd843-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="dd843-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dd843-105">Members</span></span>  
  
|<span data-ttu-id="dd843-106">Member</span><span class="sxs-lookup"><span data-stu-id="dd843-106">Member</span></span>|<span data-ttu-id="dd843-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd843-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="dd843-108">L'intervallo di istruzioni native non corrisponde a qualsiasi area di codice speciale.</span><span class="sxs-lookup"><span data-stu-id="dd843-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="dd843-109">L'intervallo di istruzioni native corrisponde al prologo.</span><span class="sxs-lookup"><span data-stu-id="dd843-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="dd843-110">L'intervallo di istruzioni native corrisponde all'epilogo.</span><span class="sxs-lookup"><span data-stu-id="dd843-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd843-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd843-111">Requirements</span></span>  
 <span data-ttu-id="dd843-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd843-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd843-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd843-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd843-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd843-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dd843-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dd843-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd843-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd843-116">See also</span></span>

- [<span data-ttu-id="dd843-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="dd843-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="dd843-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="dd843-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
