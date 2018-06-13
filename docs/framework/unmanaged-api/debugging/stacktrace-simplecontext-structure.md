---
title: Struttura StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf2ba752ace49ae288857dc22819a8e7e429a34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424053"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="e55ad-102">Struttura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="e55ad-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="e55ad-103">Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="e55ad-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e55ad-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e55ad-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e55ad-105">Members</span></span>  
  
|<span data-ttu-id="e55ad-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e55ad-106">Member</span></span>|<span data-ttu-id="e55ad-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e55ad-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="e55ad-108">Il puntatore dello stack o il puntatore dello stack invio (ESP) x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="e55ad-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="e55ad-109">L'offset di frame o il registro EBP x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="e55ad-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="e55ad-110">Il puntatore all'istruzione o il puntatore all'istruzione invio (EIP) x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="e55ad-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e55ad-111">Note</span><span class="sxs-lookup"><span data-stu-id="e55ad-111">Remarks</span></span>  
 <span data-ttu-id="e55ad-112">Poiché le funzioni di traccia dello stack, in genere è necessario restituire solo l'indirizzo, offset di frame e indirizzo dello stack, è possibile utilizzare facoltativamente il `SimpleContext` struttura anziché una grande `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="e55ad-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55ad-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e55ad-113">Requirements</span></span>  
 <span data-ttu-id="e55ad-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e55ad-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55ad-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="e55ad-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e55ad-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55ad-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e55ad-117">See Also</span></span>  
 [<span data-ttu-id="e55ad-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="e55ad-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e55ad-119">Debug</span><span class="sxs-lookup"><span data-stu-id="e55ad-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
