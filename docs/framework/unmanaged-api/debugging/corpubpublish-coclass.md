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
ms.openlocfilehash: e33029e8244fdfa180a79aa4a5b05b07f594d928
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860903"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="d135b-102">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="d135b-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="d135b-103">Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.</span><span class="sxs-lookup"><span data-stu-id="d135b-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d135b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d135b-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="d135b-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="d135b-105">Interfaces</span></span>  
  
|<span data-ttu-id="d135b-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="d135b-106">Interface</span></span>|<span data-ttu-id="d135b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d135b-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d135b-108">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="d135b-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="d135b-109">Fornisce metodi per la pubblicazione di informazioni sui processi e sui domini applicazione in tali processi.</span><span class="sxs-lookup"><span data-stu-id="d135b-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="d135b-110">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="d135b-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="d135b-111">Rappresenta e fornisce informazioni su un dominio applicazione in un processo.</span><span class="sxs-lookup"><span data-stu-id="d135b-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="d135b-112">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="d135b-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="d135b-113">Fornisce metodi che attraversano una raccolta di domini applicazione attualmente presenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="d135b-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="d135b-114">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="d135b-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="d135b-115">Rappresenta un processo in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="d135b-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="d135b-116">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="d135b-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="d135b-117">Fornisce metodi che attraversano una raccolta di processi in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="d135b-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d135b-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d135b-118">Remarks</span></span>  
 <span data-ttu-id="d135b-119">Uno scenario di pubblicazione tipico prevede lo sviluppatore che desidera eseguire il debug di codice gestito in esecuzione in un computer all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d135b-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="d135b-120">L'ambiente host può eseguire più di un dominio applicazione all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="d135b-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="d135b-121">Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o un altro mezzo per elencare tutti i processi in esecuzione nel computer e selezionare un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="d135b-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="d135b-122">L'elenco deve includere tutti i domini applicazione all'interno dei processi che eseguono codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d135b-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="d135b-123">Lo sviluppatore può quindi identificare il dominio dell'applicazione specifico e alleghiare un debugger a tale dominio.</span><span class="sxs-lookup"><span data-stu-id="d135b-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d135b-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d135b-124">Requirements</span></span>  
 <span data-ttu-id="d135b-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d135b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d135b-126">**Intestazione:** CorPub. idl</span><span class="sxs-lookup"><span data-stu-id="d135b-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="d135b-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d135b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d135b-128">**Versioni .NET Framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d135b-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d135b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d135b-129">See also</span></span>

- [<span data-ttu-id="d135b-130">Debug</span><span class="sxs-lookup"><span data-stu-id="d135b-130">Debugging</span></span>](index.md)
