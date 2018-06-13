---
title: Enumerazione CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa8bbcf4d8e5aadee6a4250d23842187d6c2af09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405486"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="5eb34-102">Enumerazione CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="5eb34-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="5eb34-103">Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5eb34-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5eb34-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="5eb34-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5eb34-105">Members</span></span>  
  
|<span data-ttu-id="5eb34-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5eb34-106">Member</span></span>|<span data-ttu-id="5eb34-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5eb34-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="5eb34-108">Indica che l'evento di debug è un'eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="5eb34-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eb34-109">Note</span><span class="sxs-lookup"><span data-stu-id="5eb34-109">Remarks</span></span>  
 <span data-ttu-id="5eb34-110">Il [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo include un `dwFlags` parametro che fornisce informazioni aggiuntive su un evento di debug e il cui valore è dipendente dall'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5eb34-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="5eb34-111">L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5eb34-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5eb34-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5eb34-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eb34-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5eb34-113">Requirements</span></span>  
 <span data-ttu-id="5eb34-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eb34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb34-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5eb34-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5eb34-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5eb34-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eb34-117">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb34-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb34-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eb34-118">See Also</span></span>  
 [<span data-ttu-id="5eb34-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="5eb34-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
