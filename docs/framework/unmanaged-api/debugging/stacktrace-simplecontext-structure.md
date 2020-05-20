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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420688"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="09c71-102">Struttura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="09c71-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="09c71-103">Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="09c71-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c71-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09c71-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="09c71-105">Membri</span><span class="sxs-lookup"><span data-stu-id="09c71-105">Members</span></span>  
  
|<span data-ttu-id="09c71-106">Membro</span><span class="sxs-lookup"><span data-stu-id="09c71-106">Member</span></span>|<span data-ttu-id="09c71-107">Description</span><span class="sxs-lookup"><span data-stu-id="09c71-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="09c71-108">Il puntatore dello stack o il puntatore di stack di immissione (ESP) sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="09c71-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="09c71-109">Offset del frame oppure il registro EBP sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="09c71-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="09c71-110">Puntatore all'istruzione oppure il puntatore all'istruzione Enter (PEI) sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="09c71-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09c71-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="09c71-111">Remarks</span></span>  
 <span data-ttu-id="09c71-112">Poiché le funzioni di analisi dello stack in genere devono restituire solo l'indirizzo, l'offset del frame e l'indirizzo dello stack, è possibile usare facoltativamente la `SimpleContext` struttura anziché una struttura di grandi dimensioni `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="09c71-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c71-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09c71-113">Requirements</span></span>  
 <span data-ttu-id="09c71-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c71-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c71-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="09c71-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="09c71-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09c71-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c71-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09c71-117">See also</span></span>

- [<span data-ttu-id="09c71-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="09c71-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="09c71-119">Debug</span><span class="sxs-lookup"><span data-stu-id="09c71-119">Debugging</span></span>](index.md)
