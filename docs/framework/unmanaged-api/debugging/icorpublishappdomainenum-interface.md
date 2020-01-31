---
title: Interfaccia ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790668"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="58589-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="58589-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="58589-103">Sottoclasse dell'interfaccia [ICorPublishEnum](icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishAppDomain](icorpublishappdomain-interface.md) attualmente presenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="58589-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58589-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="58589-104">Methods</span></span>  
  
|<span data-ttu-id="58589-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="58589-105">Method</span></span>|<span data-ttu-id="58589-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58589-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58589-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="58589-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="58589-108">Ottiene il numero specificato di istanze di `ICorPublishAppDomain` dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="58589-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58589-109">Note</span><span class="sxs-lookup"><span data-stu-id="58589-109">Remarks</span></span>  
 <span data-ttu-id="58589-110">L'interfaccia `ICorPublishAppDomainEnum` implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="58589-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58589-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="58589-111">Requirements</span></span>  
 <span data-ttu-id="58589-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58589-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58589-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="58589-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="58589-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58589-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58589-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58589-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58589-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58589-116">See also</span></span>

- [<span data-ttu-id="58589-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="58589-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="58589-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="58589-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
