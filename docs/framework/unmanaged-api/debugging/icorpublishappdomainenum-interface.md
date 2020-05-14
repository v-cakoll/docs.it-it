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
ms.openlocfilehash: a48e20413f466e25a9145e9dbf1ba93d90155770
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397037"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="37783-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="37783-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="37783-103">Sottoclasse dell'interfaccia [ICorPublishEnum](icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishAppDomain](icorpublishappdomain-interface.md) attualmente presenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="37783-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37783-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="37783-104">Methods</span></span>  
  
|<span data-ttu-id="37783-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="37783-105">Method</span></span>|<span data-ttu-id="37783-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37783-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37783-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="37783-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="37783-108">Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="37783-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37783-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="37783-109">Remarks</span></span>  
 <span data-ttu-id="37783-110">L' `ICorPublishAppDomainEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37783-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37783-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37783-111">Requirements</span></span>  
 <span data-ttu-id="37783-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37783-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37783-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="37783-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="37783-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37783-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37783-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37783-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37783-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="37783-116">See also</span></span>

- [<span data-ttu-id="37783-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="37783-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="37783-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="37783-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
