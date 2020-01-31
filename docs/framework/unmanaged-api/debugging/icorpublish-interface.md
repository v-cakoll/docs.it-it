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
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790718"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="5ee58-102">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="5ee58-102">ICorPublish Interface</span></span>
<span data-ttu-id="5ee58-103">Funge da interfaccia generale per la pubblicazione di informazioni sui processi e sulle informazioni sui domini applicazione in tali processi.</span><span class="sxs-lookup"><span data-stu-id="5ee58-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ee58-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5ee58-104">Methods</span></span>  
  
|<span data-ttu-id="5ee58-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5ee58-105">Method</span></span>|<span data-ttu-id="5ee58-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ee58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ee58-107">Metodo EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="5ee58-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="5ee58-108">Ottiene un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che contiene i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="5ee58-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="5ee58-109">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="5ee58-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="5ee58-110">Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="5ee58-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ee58-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5ee58-111">Requirements</span></span>  
 <span data-ttu-id="5ee58-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee58-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5ee58-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5ee58-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee58-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee58-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee58-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ee58-116">See also</span></span>

- [<span data-ttu-id="5ee58-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5ee58-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5ee58-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="5ee58-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
