---
title: Interfaccia ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790618"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="fa29e-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="fa29e-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="fa29e-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati nella pubblicazione di informazioni sui processi e sui domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fa29e-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa29e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fa29e-104">Methods</span></span>  
  
|<span data-ttu-id="fa29e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fa29e-105">Method</span></span>|<span data-ttu-id="fa29e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa29e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa29e-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="fa29e-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="fa29e-108">Crea una copia di questo oggetto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="fa29e-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="fa29e-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="fa29e-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="fa29e-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fa29e-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="fa29e-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="fa29e-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="fa29e-112">Sposta il cursore di all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fa29e-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="fa29e-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="fa29e-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="fa29e-114">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="fa29e-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa29e-115">Note</span><span class="sxs-lookup"><span data-stu-id="fa29e-115">Remarks</span></span>  
 <span data-ttu-id="fa29e-116">Gli enumeratori seguenti derivano da `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="fa29e-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="fa29e-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="fa29e-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="fa29e-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="fa29e-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="fa29e-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fa29e-119">Requirements</span></span>  
 <span data-ttu-id="fa29e-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa29e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa29e-121">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="fa29e-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fa29e-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa29e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa29e-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa29e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa29e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa29e-124">See also</span></span>

- [<span data-ttu-id="fa29e-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="fa29e-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="fa29e-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fa29e-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
