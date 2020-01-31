---
title: Enumerazione CorDebugMappingResult
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: 317dc2fe8403ae25949410423f1a28ad365caf6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789303"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="cc28c-102">Enumerazione CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="cc28c-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="cc28c-103">Fornisce informazioni su come è stato ottenuto il valore del puntatore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="cc28c-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc28c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc28c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="cc28c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="cc28c-105">Members</span></span>  
  
|<span data-ttu-id="cc28c-106">Member</span><span class="sxs-lookup"><span data-stu-id="cc28c-106">Member</span></span>|<span data-ttu-id="cc28c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc28c-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="cc28c-108">Il codice nativo è nel prologo, quindi il valore dell'indirizzo IP è 0.</span><span class="sxs-lookup"><span data-stu-id="cc28c-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="cc28c-109">Il codice nativo si trova in un epilogo, quindi il valore dell'indirizzo IP è l'indirizzo dell'ultima istruzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="cc28c-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="cc28c-110">Non sono disponibili informazioni di mapping per il metodo, quindi il valore dell'indirizzo IP è 0.</span><span class="sxs-lookup"><span data-stu-id="cc28c-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="cc28c-111">Sebbene esistano informazioni di mapping per il metodo, non è possibile eseguire il mapping dell'indirizzo corrente al codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="cc28c-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="cc28c-112">Il valore dell'indirizzo IP è 0.</span><span class="sxs-lookup"><span data-stu-id="cc28c-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="cc28c-113">Il metodo esegue il mapping esatto al codice MSIL o il frame è stato interpretato, quindi il valore dell'indirizzo IP è accurato.</span><span class="sxs-lookup"><span data-stu-id="cc28c-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="cc28c-114">Il mapping del metodo è stato eseguito correttamente, ma il valore dell'indirizzo IP potrebbe essere approssimativo.</span><span class="sxs-lookup"><span data-stu-id="cc28c-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc28c-115">Note</span><span class="sxs-lookup"><span data-stu-id="cc28c-115">Remarks</span></span>  
 <span data-ttu-id="cc28c-116">È possibile usare il metodo [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) per ottenere il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="cc28c-116">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc28c-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cc28c-117">Requirements</span></span>  
 <span data-ttu-id="cc28c-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc28c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc28c-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc28c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc28c-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc28c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc28c-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc28c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc28c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc28c-122">See also</span></span>

- [<span data-ttu-id="cc28c-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="cc28c-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
