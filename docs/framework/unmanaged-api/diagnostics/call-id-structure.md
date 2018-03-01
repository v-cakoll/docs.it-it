---
title: Struttura CALL_ID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71fd69cbcced1440839b9eedf8fbe3d8f5b90646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="callid-structure"></a><span data-ttu-id="18ba1-102">Struttura CALL_ID</span><span class="sxs-lookup"><span data-stu-id="18ba1-102">CALL_ID Structure</span></span>
<span data-ttu-id="18ba1-103">Vengono fornite informazioni a un debugger su una funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="18ba1-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="18ba1-104">Vedere il [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaccia per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="18ba1-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ba1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18ba1-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="18ba1-106">Membri</span><span class="sxs-lookup"><span data-stu-id="18ba1-106">Members</span></span>  
  
|<span data-ttu-id="18ba1-107">Membro</span><span class="sxs-lookup"><span data-stu-id="18ba1-107">Member</span></span>|<span data-ttu-id="18ba1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18ba1-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="18ba1-109">Identifica il computer che esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="18ba1-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="18ba1-110">Identifica il processore della macchina.</span><span class="sxs-lookup"><span data-stu-id="18ba1-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="18ba1-111">Identifica il thread che sta eseguendo la chiamata.</span><span class="sxs-lookup"><span data-stu-id="18ba1-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="18ba1-112">Specifica l'indirizzo dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="18ba1-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="18ba1-113">Specifica l'indirizzo della chiamata.</span><span class="sxs-lookup"><span data-stu-id="18ba1-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="18ba1-114">Identifica il computer che esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="18ba1-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18ba1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18ba1-115">Requirements</span></span>  
 <span data-ttu-id="18ba1-116">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="18ba1-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ba1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ba1-117">See Also</span></span>  
 [<span data-ttu-id="18ba1-118">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="18ba1-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="18ba1-119">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="18ba1-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
