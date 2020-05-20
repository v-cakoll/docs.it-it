---
title: Enumerazione LoggingLevelEnum
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 62ea982f30a6a73648d9bf36722c0b5a49a68896
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420747"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="166b7-102">Enumerazione LoggingLevelEnum</span><span class="sxs-lookup"><span data-stu-id="166b7-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="166b7-103">Indica il livello di gravità di un messaggio descrittivo scritto nel registro eventi quando un thread gestito registra un evento.</span><span class="sxs-lookup"><span data-stu-id="166b7-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="166b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="166b7-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="166b7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="166b7-105">Members</span></span>  
  
|<span data-ttu-id="166b7-106">Membro</span><span class="sxs-lookup"><span data-stu-id="166b7-106">Member</span></span>|<span data-ttu-id="166b7-107">Description</span><span class="sxs-lookup"><span data-stu-id="166b7-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="166b7-108">Il messaggio è un livello di traccia 0.</span><span class="sxs-lookup"><span data-stu-id="166b7-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="166b7-109">Il messaggio è un livello di traccia 1.</span><span class="sxs-lookup"><span data-stu-id="166b7-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="166b7-110">Il messaggio è un livello di traccia 2.</span><span class="sxs-lookup"><span data-stu-id="166b7-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="166b7-111">Il messaggio è un livello di traccia 3.</span><span class="sxs-lookup"><span data-stu-id="166b7-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="166b7-112">Il messaggio è un livello di traccia 4.</span><span class="sxs-lookup"><span data-stu-id="166b7-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="166b7-113">Il messaggio è un livello di stato 0.</span><span class="sxs-lookup"><span data-stu-id="166b7-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="166b7-114">Il messaggio è un livello di stato 1.</span><span class="sxs-lookup"><span data-stu-id="166b7-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="166b7-115">Il messaggio è un livello di stato 2.</span><span class="sxs-lookup"><span data-stu-id="166b7-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="166b7-116">Il messaggio è un livello di stato 3.</span><span class="sxs-lookup"><span data-stu-id="166b7-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="166b7-117">Il messaggio è un livello di stato 4.</span><span class="sxs-lookup"><span data-stu-id="166b7-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="166b7-118">Il messaggio è un livello di avviso.</span><span class="sxs-lookup"><span data-stu-id="166b7-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="166b7-119">Il messaggio è un livello di errore.</span><span class="sxs-lookup"><span data-stu-id="166b7-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="166b7-120">Il messaggio è un livello di panico.</span><span class="sxs-lookup"><span data-stu-id="166b7-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="166b7-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="166b7-121">Remarks</span></span>  
 <span data-ttu-id="166b7-122">Il Common Language Runtime (CLR) chiama il metodo [ICorDebugManagedCallback:: LogMessage](icordebugmanagedcallback-logmessage-method.md) per notificare al debugger che un thread gestito ha registrato un evento.</span><span class="sxs-lookup"><span data-stu-id="166b7-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="166b7-123">CLR passa un valore dell' `LoggingLevelEnum` enumerazione per indicare il livello di gravità del messaggio scritto dal thread gestito nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="166b7-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="166b7-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="166b7-124">Requirements</span></span>  
 <span data-ttu-id="166b7-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="166b7-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="166b7-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="166b7-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="166b7-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="166b7-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="166b7-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="166b7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166b7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="166b7-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="166b7-130">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="166b7-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
