---
title: Interfaccia ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076341"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="c42ee-102">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="c42ee-102">ICorPublish Interface</span></span>
<span data-ttu-id="c42ee-103">Funge da interfaccia generale per la pubblicazione di informazioni sui processi e le informazioni sui domini dell'applicazione in tali processi.</span><span class="sxs-lookup"><span data-stu-id="c42ee-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c42ee-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c42ee-104">Methods</span></span>  
  
|<span data-ttu-id="c42ee-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c42ee-105">Method</span></span>|<span data-ttu-id="c42ee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c42ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c42ee-107">Metodo EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="c42ee-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="c42ee-108">Ottiene un' [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che contiene i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="c42ee-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="c42ee-109">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="c42ee-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="c42ee-110">Ottiene un' [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) istanza che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="c42ee-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c42ee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c42ee-111">Requirements</span></span>  
 <span data-ttu-id="c42ee-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c42ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c42ee-113">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c42ee-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c42ee-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c42ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c42ee-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c42ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42ee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c42ee-116">See also</span></span>

- [<span data-ttu-id="c42ee-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c42ee-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c42ee-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="c42ee-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
