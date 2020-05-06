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
ms.openlocfilehash: a90ddd27834e7614c1827d606a9955b4d6c53127
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795976"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="cc203-102">Enumerazione CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="cc203-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="cc203-103">Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="cc203-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc203-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc203-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="cc203-105">Members</span><span class="sxs-lookup"><span data-stu-id="cc203-105">Members</span></span>  
  
|<span data-ttu-id="cc203-106">Membro</span><span class="sxs-lookup"><span data-stu-id="cc203-106">Member</span></span>|<span data-ttu-id="cc203-107">Description</span><span class="sxs-lookup"><span data-stu-id="cc203-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="cc203-108">Indica che l'evento di debug è un'eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="cc203-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc203-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cc203-109">Remarks</span></span>  
 <span data-ttu-id="cc203-110">Il metodo [Metodo icordebugprocess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) include un `dwFlags` parametro che fornisce informazioni aggiuntive su un evento di debug e il cui valore dipende dall'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cc203-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="cc203-111">L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="cc203-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc203-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cc203-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc203-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc203-113">Requirements</span></span>  
 <span data-ttu-id="cc203-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc203-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc203-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc203-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc203-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc203-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc203-117">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc203-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc203-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc203-118">See also</span></span>

- [<span data-ttu-id="cc203-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="cc203-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
