---
title: Interfaccia ICorPublish
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish
helpviewer_keywords: ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8eb3bd2da9529a681f7f3a09ef7eb78c776cc302
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublish-interface"></a><span data-ttu-id="86dbf-102">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="86dbf-102">ICorPublish Interface</span></span>
<span data-ttu-id="86dbf-103">Funge da interfaccia generale per la pubblicazione di informazioni sui processi e le informazioni sui domini dell'applicazione in tali processi.</span><span class="sxs-lookup"><span data-stu-id="86dbf-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86dbf-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="86dbf-104">Methods</span></span>  
  
|<span data-ttu-id="86dbf-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="86dbf-105">Method</span></span>|<span data-ttu-id="86dbf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86dbf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86dbf-107">EnumProcesses (metodo)</span><span class="sxs-lookup"><span data-stu-id="86dbf-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="86dbf-108">Ottiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che contiene i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="86dbf-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="86dbf-109">GetProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="86dbf-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="86dbf-110">Ottiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) istanza che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="86dbf-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86dbf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86dbf-111">Requirements</span></span>  
 <span data-ttu-id="86dbf-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86dbf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86dbf-113">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="86dbf-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="86dbf-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86dbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86dbf-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86dbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86dbf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86dbf-116">See Also</span></span>  
 [<span data-ttu-id="86dbf-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="86dbf-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="86dbf-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="86dbf-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
