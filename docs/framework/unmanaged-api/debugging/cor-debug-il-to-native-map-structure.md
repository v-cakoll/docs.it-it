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
ms.openlocfilehash: babb1ace1385c241b782691f22bfb4fbb689e310
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274067"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="b6e03-102">Struttura COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="b6e03-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="b6e03-103">Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b6e03-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6e03-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="b6e03-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b6e03-105">Members</span></span>  
  
|<span data-ttu-id="b6e03-106">Member</span><span class="sxs-lookup"><span data-stu-id="b6e03-106">Member</span></span>|<span data-ttu-id="b6e03-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6e03-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="b6e03-108">Offset del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="b6e03-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="b6e03-109">Offset dell'inizio del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b6e03-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="b6e03-110">Offset della fine del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b6e03-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6e03-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6e03-111">Requirements</span></span>  
 <span data-ttu-id="b6e03-112">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6e03-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e03-113">**Intestazione:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b6e03-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="b6e03-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6e03-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6e03-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e03-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e03-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6e03-116">See also</span></span>

- [<span data-ttu-id="b6e03-117">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="b6e03-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="b6e03-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="b6e03-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="b6e03-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="b6e03-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b6e03-120">Debug</span><span class="sxs-lookup"><span data-stu-id="b6e03-120">Debugging</span></span>](index.md)
