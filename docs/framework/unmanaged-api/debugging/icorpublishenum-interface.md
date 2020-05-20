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
ms.openlocfilehash: acbc37d0f49af21c60ff6989932c5d341673512b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421176"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="2c3fd-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="2c3fd-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="2c3fd-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati nella pubblicazione di informazioni sui processi e sui domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c3fd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2c3fd-104">Methods</span></span>  
  
|<span data-ttu-id="2c3fd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2c3fd-105">Method</span></span>|<span data-ttu-id="2c3fd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c3fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c3fd-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="2c3fd-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="2c3fd-108">Crea una copia dell'oggetto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="2c3fd-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="2c3fd-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="2c3fd-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="2c3fd-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="2c3fd-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="2c3fd-112">Sposta il cursore di all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="2c3fd-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="2c3fd-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="2c3fd-114">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c3fd-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c3fd-115">Remarks</span></span>  
 <span data-ttu-id="2c3fd-116">Gli enumeratori seguenti derivano da `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="2c3fd-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="2c3fd-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="2c3fd-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="2c3fd-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="2c3fd-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="2c3fd-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c3fd-119">Requirements</span></span>  
 <span data-ttu-id="2c3fd-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c3fd-121">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2c3fd-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2c3fd-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c3fd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c3fd-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c3fd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c3fd-124">See also</span></span>

- [<span data-ttu-id="2c3fd-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="2c3fd-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="2c3fd-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2c3fd-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
