---
title: Enumerazione CorDebugExceptionFlags
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 6ef81e224f3573021ee96ac313ec4923928dedad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789394"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="9c9a3-102">Enumerazione CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="9c9a3-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="9c9a3-103">Offre informazioni aggiuntive su un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c9a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c9a3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9c9a3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9c9a3-105">Members</span></span>  
  
|<span data-ttu-id="9c9a3-106">Member</span><span class="sxs-lookup"><span data-stu-id="9c9a3-106">Member</span></span>|<span data-ttu-id="9c9a3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c9a3-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="9c9a3-108">Nessuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="9c9a3-109">L'eccezione è intercettabile.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="9c9a3-110">È possibile che la temporizzazione dell'eccezione non consenta al debugger di intercettarla.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="9c9a3-111">Ad esempio, in assenza di codice gestito sotto il callback corrente o se l'evento di eccezione è stato generato da un allegato JIT, non è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c9a3-112">Note</span><span class="sxs-lookup"><span data-stu-id="9c9a3-112">Remarks</span></span>  
 <span data-ttu-id="9c9a3-113">È possibile che nelle versioni successive vengano aggiunti nuovi valori a questa enumerazione, quindi è necessario predisporre codice che usa `CorDebugExceptionFlags` per i valori non previsti.</span><span class="sxs-lookup"><span data-stu-id="9c9a3-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c9a3-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9c9a3-114">Requirements</span></span>  
 <span data-ttu-id="9c9a3-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c9a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c9a3-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c9a3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c9a3-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c9a3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c9a3-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c9a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c9a3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c9a3-119">See also</span></span>

- [<span data-ttu-id="9c9a3-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9c9a3-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
