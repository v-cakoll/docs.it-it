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
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420630"
---
# <a name="call_id-structure"></a><span data-ttu-id="809e3-102">Struttura CALL_ID</span><span class="sxs-lookup"><span data-stu-id="809e3-102">CALL_ID Structure</span></span>
<span data-ttu-id="809e3-103">Fornisce informazioni a un debugger relativo a una funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="809e3-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="809e3-104">Per ulteriori informazioni, vedere l'interfaccia [INotifySink2](inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="809e3-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809e3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="809e3-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="809e3-106">Membri</span><span class="sxs-lookup"><span data-stu-id="809e3-106">Members</span></span>  
  
|<span data-ttu-id="809e3-107">Membro</span><span class="sxs-lookup"><span data-stu-id="809e3-107">Member</span></span>|<span data-ttu-id="809e3-108">Description</span><span class="sxs-lookup"><span data-stu-id="809e3-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="809e3-109">Identifica il computer che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="809e3-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="809e3-110">Identifica il processore del computer.</span><span class="sxs-lookup"><span data-stu-id="809e3-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="809e3-111">Identifica il thread che esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="809e3-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="809e3-112">Specifica l'indirizzo dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="809e3-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="809e3-113">Specifica l'indirizzo della chiamata.</span><span class="sxs-lookup"><span data-stu-id="809e3-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="809e3-114">Identifica il computer che eseguirà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="809e3-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="809e3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="809e3-115">Requirements</span></span>  
 <span data-ttu-id="809e3-116">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="809e3-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809e3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="809e3-117">See also</span></span>

- [<span data-ttu-id="809e3-118">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="809e3-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="809e3-119">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="809e3-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
