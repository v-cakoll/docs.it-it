---
title: Struttura StackOverflowInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowInfo
helpviewer_keywords: StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 102f744ecc769a10161cd20767e8e49c838252a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="f8a40-102">Struttura StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="f8a40-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="f8a40-103">Archivia il tipo di overflow che si sono verificati e informazioni sull'eccezione generata a causa dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="f8a40-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8a40-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f8a40-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f8a40-105">Members</span></span>  
  
|<span data-ttu-id="f8a40-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f8a40-106">Member</span></span>|<span data-ttu-id="f8a40-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8a40-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="f8a40-108">Il valore di [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumerazione che specifica il tipo di overflow.</span><span class="sxs-lookup"><span data-stu-id="f8a40-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="f8a40-109">Un puntatore a un Win32 `EXCEPTION_POINTERS` oggetto che contiene un record di eccezione con una descrizione indipendente dal computer di un'eccezione e un record di contesto con una descrizione di dipendenti dal computer del contesto del processore al momento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f8a40-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8a40-110">Note</span><span class="sxs-lookup"><span data-stu-id="f8a40-110">Remarks</span></span>  
 <span data-ttu-id="f8a40-111">A `StackOverflowInfo` oggetto viene passato per il [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) metodo per `Event_StackOverflow` eventi.</span><span class="sxs-lookup"><span data-stu-id="f8a40-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a40-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8a40-112">Requirements</span></span>  
 <span data-ttu-id="f8a40-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a40-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a40-114">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="f8a40-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f8a40-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8a40-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8a40-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a40-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a40-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8a40-117">See Also</span></span>  
 [<span data-ttu-id="f8a40-118">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="f8a40-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
