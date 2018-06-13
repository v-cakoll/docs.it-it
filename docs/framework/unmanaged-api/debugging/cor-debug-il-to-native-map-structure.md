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
ms.openlocfilehash: 2ea9a75ae9316c18439f6c2b728b47deacef9228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404737"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="9a2d9-102">Struttura COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="9a2d9-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="9a2d9-103">Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9a2d9-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a2d9-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="9a2d9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9a2d9-105">Members</span></span>  
  
|<span data-ttu-id="9a2d9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9a2d9-106">Member</span></span>|<span data-ttu-id="9a2d9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a2d9-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="9a2d9-108">L'offset del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="9a2d9-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="9a2d9-109">L'offset dell'inizio del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9a2d9-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="9a2d9-110">L'offset della fine del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9a2d9-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a2d9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a2d9-111">Requirements</span></span>  
 <span data-ttu-id="9a2d9-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a2d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a2d9-113">**Intestazione:** Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="9a2d9-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="9a2d9-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9a2d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a2d9-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a2d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2d9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a2d9-116">See Also</span></span>  
 [<span data-ttu-id="9a2d9-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="9a2d9-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="9a2d9-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="9a2d9-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="9a2d9-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="9a2d9-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9a2d9-120">Debug</span><span class="sxs-lookup"><span data-stu-id="9a2d9-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
