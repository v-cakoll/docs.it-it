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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7b9b25673685dde8b75702c80f525515917ae1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078707"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="a94e7-102">Enumerazione CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="a94e7-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="a94e7-103">Offre informazioni aggiuntive su un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a94e7-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a94e7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a94e7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a94e7-105">Members</span></span>  
  
|<span data-ttu-id="a94e7-106">Member</span><span class="sxs-lookup"><span data-stu-id="a94e7-106">Member</span></span>|<span data-ttu-id="a94e7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94e7-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="a94e7-108">Nessuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="a94e7-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="a94e7-109">L'eccezione è intercettabile.</span><span class="sxs-lookup"><span data-stu-id="a94e7-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="a94e7-110">È possibile che la temporizzazione dell'eccezione non consenta al debugger di intercettarla.</span><span class="sxs-lookup"><span data-stu-id="a94e7-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="a94e7-111">Ad esempio, in assenza di codice gestito sotto il callback corrente o se l'evento di eccezione è stato generato da un allegato JIT, non è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a94e7-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a94e7-112">Note</span><span class="sxs-lookup"><span data-stu-id="a94e7-112">Remarks</span></span>  
 <span data-ttu-id="a94e7-113">È possibile che nelle versioni successive vengano aggiunti nuovi valori a questa enumerazione, quindi è necessario predisporre codice che usa `CorDebugExceptionFlags` per i valori non previsti.</span><span class="sxs-lookup"><span data-stu-id="a94e7-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94e7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a94e7-114">Requirements</span></span>  
 <span data-ttu-id="a94e7-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94e7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94e7-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a94e7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a94e7-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a94e7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a94e7-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94e7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a94e7-119">See also</span></span>

- [<span data-ttu-id="a94e7-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="a94e7-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
