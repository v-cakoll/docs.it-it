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
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142051"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="57a24-102">Struttura COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="57a24-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="57a24-103">Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="57a24-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57a24-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="57a24-105">Membri</span><span class="sxs-lookup"><span data-stu-id="57a24-105">Members</span></span>  
  
|<span data-ttu-id="57a24-106">Member</span><span class="sxs-lookup"><span data-stu-id="57a24-106">Member</span></span>|<span data-ttu-id="57a24-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57a24-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="57a24-108">L'offset del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="57a24-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="57a24-109">L'offset dell'inizio del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="57a24-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="57a24-110">L'offset della fine del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="57a24-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57a24-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57a24-111">Requirements</span></span>  
 <span data-ttu-id="57a24-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57a24-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a24-113">**Intestazione:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="57a24-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="57a24-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57a24-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57a24-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a24-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a24-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57a24-116">See also</span></span>

- [<span data-ttu-id="57a24-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="57a24-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="57a24-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="57a24-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="57a24-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="57a24-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="57a24-120">Debug</span><span class="sxs-lookup"><span data-stu-id="57a24-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
