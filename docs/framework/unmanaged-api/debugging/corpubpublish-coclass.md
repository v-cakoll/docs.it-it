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
ms.openlocfilehash: 7d1ca8ea9d00de8a07c67977cf108c50268802e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739350"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="675a6-102">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="675a6-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="675a6-103">Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.</span><span class="sxs-lookup"><span data-stu-id="675a6-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="675a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="675a6-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="675a6-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="675a6-105">Interfaces</span></span>  
  
|<span data-ttu-id="675a6-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="675a6-106">Interface</span></span>|<span data-ttu-id="675a6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="675a6-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="675a6-108">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="675a6-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="675a6-109">Fornisce metodi per la pubblicazione delle informazioni sui processi e i domini applicazione tali processi.</span><span class="sxs-lookup"><span data-stu-id="675a6-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="675a6-110">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="675a6-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="675a6-111">Rappresenta e fornisce informazioni su un dominio dell'applicazione in un processo.</span><span class="sxs-lookup"><span data-stu-id="675a6-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="675a6-112">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="675a6-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="675a6-113">Fornisce metodi che scorrono una raccolta di domini applicazione attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="675a6-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="675a6-114">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="675a6-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="675a6-115">Rappresenta un processo in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="675a6-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="675a6-116">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="675a6-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="675a6-117">Fornisce metodi che scorrono una raccolta di processi in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="675a6-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="675a6-118">Note</span><span class="sxs-lookup"><span data-stu-id="675a6-118">Remarks</span></span>  
 <span data-ttu-id="675a6-119">Un tipico scenario di pubblicazione comporta uno sviluppatore che desidera eseguire il debug di codice gestito che è in esecuzione in un computer all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="675a6-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="675a6-120">L'ambiente di hosting potrebbe essere più di un dominio applicazione all'interno di un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="675a6-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="675a6-121">Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o in altro modo per elencare tutti i processi in esecuzione nel computer e scegliere un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="675a6-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="675a6-122">L'elenco dovrebbe includere tutti i domini dell'applicazione all'interno di processi che eseguono il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="675a6-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="675a6-123">Lo sviluppatore può quindi identificare il dominio applicazione specifica e collegare un debugger per tale dominio.</span><span class="sxs-lookup"><span data-stu-id="675a6-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="675a6-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="675a6-124">Requirements</span></span>  
 <span data-ttu-id="675a6-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="675a6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="675a6-126">**Intestazione:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="675a6-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="675a6-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="675a6-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="675a6-128">**Versioni di .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="675a6-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675a6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="675a6-129">See also</span></span>

- [<span data-ttu-id="675a6-130">Debug</span><span class="sxs-lookup"><span data-stu-id="675a6-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
