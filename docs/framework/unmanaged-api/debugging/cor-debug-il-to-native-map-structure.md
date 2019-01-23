---
title: Struttura COR_DEBUG_IL_TO_NATIVE_MAP
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56d4255b06f1317c87685737e4ee4021c37a77f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555011"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="6cfe8-102">Struttura COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="6cfe8-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="6cfe8-103">Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cfe8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cfe8-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="6cfe8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6cfe8-105">Members</span></span>  
  
|<span data-ttu-id="6cfe8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6cfe8-106">Member</span></span>|<span data-ttu-id="6cfe8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cfe8-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="6cfe8-108">L'offset del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="6cfe8-109">L'offset dell'inizio del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="6cfe8-110">L'offset della fine del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6cfe8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6cfe8-111">Requirements</span></span>  
 <span data-ttu-id="6cfe8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cfe8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cfe8-113">**Intestazione:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="6cfe8-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="6cfe8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cfe8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cfe8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cfe8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cfe8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cfe8-116">See also</span></span>
- [<span data-ttu-id="6cfe8-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="6cfe8-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="6cfe8-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="6cfe8-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="6cfe8-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="6cfe8-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="6cfe8-120">Debug</span><span class="sxs-lookup"><span data-stu-id="6cfe8-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
