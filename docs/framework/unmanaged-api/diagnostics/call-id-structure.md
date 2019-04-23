---
title: Struttura CALL_ID
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6fa729b131d12b2825a2def700fd918ce8acc40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220175"
---
# <a name="callid-structure"></a><span data-ttu-id="a8e60-102">Struttura CALL_ID</span><span class="sxs-lookup"><span data-stu-id="a8e60-102">CALL_ID Structure</span></span>
<span data-ttu-id="a8e60-103">Fornisce informazioni relative a una funzione che viene chiamata un debugger.</span><span class="sxs-lookup"><span data-stu-id="a8e60-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="a8e60-104">Vedere le [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaccia per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="a8e60-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8e60-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a8e60-106">Membri</span><span class="sxs-lookup"><span data-stu-id="a8e60-106">Members</span></span>  
  
|<span data-ttu-id="a8e60-107">Member</span><span class="sxs-lookup"><span data-stu-id="a8e60-107">Member</span></span>|<span data-ttu-id="a8e60-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8e60-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="a8e60-109">Identifica il computer che esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a8e60-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="a8e60-110">Identifica il processore della macchina.</span><span class="sxs-lookup"><span data-stu-id="a8e60-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="a8e60-111">Identifica il thread che sta eseguendo la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a8e60-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="a8e60-112">Specifica l'indirizzo dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="a8e60-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="a8e60-113">Specifica l'indirizzo della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a8e60-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="a8e60-114">Identifica il computer che eseguirà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a8e60-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8e60-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8e60-115">Requirements</span></span>  
 <span data-ttu-id="a8e60-116">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a8e60-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e60-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8e60-117">See also</span></span>

- [<span data-ttu-id="a8e60-118">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="a8e60-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="a8e60-119">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a8e60-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
