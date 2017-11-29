---
title: Struttura USER_THREAD
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: USER_THREAD
api_location: diasymreader.dll
api_type: COM
f1_keywords: USER_THREAD
helpviewer_keywords: USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d93002fe5460bfdb36d4e11c74410677b46a98d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="b1c32-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="b1c32-102">USER_THREAD Structure</span></span>
<span data-ttu-id="b1c32-103">Vengono fornite informazioni a un debugger su un thread.</span><span class="sxs-lookup"><span data-stu-id="b1c32-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="b1c32-104">Per ulteriori informazioni, vedere il [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="b1c32-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c32-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1c32-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="b1c32-106">Membri</span><span class="sxs-lookup"><span data-stu-id="b1c32-106">Members</span></span>  
  
|<span data-ttu-id="b1c32-107">Membro</span><span class="sxs-lookup"><span data-stu-id="b1c32-107">Member</span></span>|<span data-ttu-id="b1c32-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1c32-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="b1c32-109">Indirizzo del buffer dei thread.</span><span class="sxs-lookup"><span data-stu-id="b1c32-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="b1c32-110">Lunghezza del buffer dei thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="b1c32-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="b1c32-111">ID del thread.</span><span class="sxs-lookup"><span data-stu-id="b1c32-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1c32-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1c32-112">Requirements</span></span>  
 <span data-ttu-id="b1c32-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="b1c32-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c32-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1c32-114">See Also</span></span>  
 [<span data-ttu-id="b1c32-115">SetNotifyFilter (metodo)</span><span class="sxs-lookup"><span data-stu-id="b1c32-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="b1c32-116">Strutture di archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="b1c32-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
