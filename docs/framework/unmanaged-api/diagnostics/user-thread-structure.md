---
title: Struttura USER_THREAD
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
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 50533ce25812ad49d538c5a6a6c814d7a9704053
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="06a1a-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="06a1a-102">USER_THREAD Structure</span></span>
<span data-ttu-id="06a1a-103">Vengono fornite informazioni a un debugger su un thread.</span><span class="sxs-lookup"><span data-stu-id="06a1a-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="06a1a-104">Per ulteriori informazioni, vedere il [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="06a1a-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a1a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06a1a-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="06a1a-106">Membri</span><span class="sxs-lookup"><span data-stu-id="06a1a-106">Members</span></span>  
  
|<span data-ttu-id="06a1a-107">Membro</span><span class="sxs-lookup"><span data-stu-id="06a1a-107">Member</span></span>|<span data-ttu-id="06a1a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06a1a-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="06a1a-109">Indirizzo del buffer dei thread.</span><span class="sxs-lookup"><span data-stu-id="06a1a-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="06a1a-110">Lunghezza del buffer dei thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="06a1a-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="06a1a-111">ID del thread.</span><span class="sxs-lookup"><span data-stu-id="06a1a-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06a1a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06a1a-112">Requirements</span></span>  
 <span data-ttu-id="06a1a-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="06a1a-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a1a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a1a-114">See Also</span></span>  
 [<span data-ttu-id="06a1a-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="06a1a-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="06a1a-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="06a1a-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
