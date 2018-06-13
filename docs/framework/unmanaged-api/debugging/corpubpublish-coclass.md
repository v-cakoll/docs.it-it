---
title: Coclasse CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9941a9be7d9f68255636b405db29a623be8d37e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406438"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="f72e2-102">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="f72e2-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="f72e2-103">Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.</span><span class="sxs-lookup"><span data-stu-id="f72e2-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f72e2-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="f72e2-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f72e2-105">Interfaces</span></span>  
  
|<span data-ttu-id="f72e2-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="f72e2-106">Interface</span></span>|<span data-ttu-id="f72e2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f72e2-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="f72e2-108">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="f72e2-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="f72e2-109">Fornisce metodi per la pubblicazione delle informazioni sui processi e i domini applicazione di tali processi.</span><span class="sxs-lookup"><span data-stu-id="f72e2-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="f72e2-110">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="f72e2-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="f72e2-111">Rappresenta e fornisce informazioni su un dominio applicazione in un processo.</span><span class="sxs-lookup"><span data-stu-id="f72e2-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="f72e2-112">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="f72e2-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="f72e2-113">Fornisce metodi che scorrono una raccolta di domini applicazione attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="f72e2-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="f72e2-114">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="f72e2-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="f72e2-115">Rappresenta un processo in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="f72e2-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="f72e2-116">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f72e2-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="f72e2-117">Fornisce metodi che scorrono una raccolta di processi in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="f72e2-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f72e2-118">Note</span><span class="sxs-lookup"><span data-stu-id="f72e2-118">Remarks</span></span>  
 <span data-ttu-id="f72e2-119">Un tipico scenario di pubblicazione comporta uno sviluppatore che desidera eseguire il debug di codice gestito che è in esecuzione in un computer all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="f72e2-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="f72e2-120">L'ambiente host potrebbe essere più di un dominio applicazione all'interno di un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f72e2-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="f72e2-121">Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o in altro modo per visualizzare l'elenco di tutti i processi in esecuzione nel computer e scegliere un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="f72e2-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="f72e2-122">L'elenco deve includere tutti i domini applicazione all'interno di processi che eseguono codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f72e2-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="f72e2-123">Lo sviluppatore può quindi identificare il dominio di applicazione specifico e collegare un debugger a quel dominio.</span><span class="sxs-lookup"><span data-stu-id="f72e2-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72e2-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f72e2-124">Requirements</span></span>  
 <span data-ttu-id="f72e2-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72e2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72e2-126">**Intestazione:** Corpub. idl</span><span class="sxs-lookup"><span data-stu-id="f72e2-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="f72e2-127">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f72e2-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f72e2-128">**Versioni di .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72e2-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72e2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f72e2-129">See Also</span></span>  
 [<span data-ttu-id="f72e2-130">Debug</span><span class="sxs-lookup"><span data-stu-id="f72e2-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
