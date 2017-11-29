---
title: Coclasse CorpubPublish
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="fa8ea-102">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="fa8ea-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="fa8ea-103">Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa8ea-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="fa8ea-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="fa8ea-105">Interfaces</span></span>  
  
|<span data-ttu-id="fa8ea-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="fa8ea-106">Interface</span></span>|<span data-ttu-id="fa8ea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa8ea-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="fa8ea-108">ICorPublish (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="fa8ea-109">Fornisce metodi per la pubblicazione delle informazioni sui processi e i domini applicazione di tali processi.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="fa8ea-110">ICorPublishAppDomain (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="fa8ea-111">Rappresenta e fornisce informazioni su un dominio applicazione in un processo.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="fa8ea-112">ICorPublishAppDomainEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="fa8ea-113">Fornisce metodi che scorrono una raccolta di domini applicazione attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="fa8ea-114">ICorPublishProcess (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="fa8ea-115">Rappresenta un processo in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="fa8ea-116">ICorPublishProcessEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="fa8ea-117">Fornisce metodi che scorrono una raccolta di processi in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa8ea-118">Note</span><span class="sxs-lookup"><span data-stu-id="fa8ea-118">Remarks</span></span>  
 <span data-ttu-id="fa8ea-119">Un tipico scenario di pubblicazione comporta uno sviluppatore che desidera eseguire il debug di codice gestito che è in esecuzione in un computer all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="fa8ea-120">L'ambiente host potrebbe essere più di un dominio applicazione all'interno di un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="fa8ea-121">Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o in altro modo per visualizzare l'elenco di tutti i processi in esecuzione nel computer e scegliere un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="fa8ea-122">L'elenco deve includere tutti i domini applicazione all'interno di processi che eseguono codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="fa8ea-123">Lo sviluppatore può quindi identificare il dominio di applicazione specifico e collegare un debugger a quel dominio.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8ea-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa8ea-124">Requirements</span></span>  
 <span data-ttu-id="fa8ea-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa8ea-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8ea-126">**Intestazione:** Corpub. idl</span><span class="sxs-lookup"><span data-stu-id="fa8ea-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="fa8ea-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa8ea-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa8ea-128">**Versioni di .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8ea-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8ea-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa8ea-129">See Also</span></span>  
 [<span data-ttu-id="fa8ea-130">Debug</span><span class="sxs-lookup"><span data-stu-id="fa8ea-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
