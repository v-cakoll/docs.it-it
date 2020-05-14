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
ms.openlocfilehash: 1bd2f537cfa6a27c24ba91ea7caa29dc9e71a74e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396317"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="3918a-102">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="3918a-102">ICorPublish Interface</span></span>
<span data-ttu-id="3918a-103">Funge da interfaccia generale per la pubblicazione di informazioni sui processi e sulle informazioni sui domini applicazione in tali processi.</span><span class="sxs-lookup"><span data-stu-id="3918a-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3918a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3918a-104">Methods</span></span>  
  
|<span data-ttu-id="3918a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3918a-105">Method</span></span>|<span data-ttu-id="3918a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3918a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3918a-107">Metodo EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="3918a-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="3918a-108">Ottiene un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che contiene i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="3918a-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="3918a-109">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="3918a-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="3918a-110">Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="3918a-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3918a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3918a-111">Requirements</span></span>  
 <span data-ttu-id="3918a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3918a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3918a-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3918a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3918a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3918a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3918a-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3918a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3918a-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3918a-116">See also</span></span>

- [<span data-ttu-id="3918a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3918a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3918a-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="3918a-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
