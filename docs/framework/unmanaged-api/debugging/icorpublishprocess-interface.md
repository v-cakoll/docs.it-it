---
title: Interfaccia ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421085"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="9c04f-102">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="9c04f-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="9c04f-103">Fornisce metodi che accedono alle informazioni da visualizzare su un processo.</span><span class="sxs-lookup"><span data-stu-id="9c04f-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c04f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9c04f-104">Methods</span></span>  
  
|<span data-ttu-id="9c04f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9c04f-105">Method</span></span>|<span data-ttu-id="9c04f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c04f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c04f-107">Metodo EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="9c04f-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="9c04f-108">Ottiene un'istanza di [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) che contiene i domini applicazione nel processo a cui fa riferimento questo oggetto `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9c04f-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9c04f-109">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="9c04f-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="9c04f-110">Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo oggetto `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9c04f-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9c04f-111">Metodo GetProcessID</span><span class="sxs-lookup"><span data-stu-id="9c04f-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="9c04f-112">Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento questo oggetto `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9c04f-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9c04f-113">Metodo IsManaged</span><span class="sxs-lookup"><span data-stu-id="9c04f-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="9c04f-114">Ottiene un valore che indica se il processo a cui fa riferimento questo oggetto `ICorPublishProcess` è noto per l'esecuzione di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="9c04f-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c04f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c04f-115">Requirements</span></span>  
 <span data-ttu-id="9c04f-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c04f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c04f-117">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="9c04f-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9c04f-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c04f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c04f-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c04f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c04f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c04f-120">See also</span></span>

- [<span data-ttu-id="9c04f-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9c04f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9c04f-122">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="9c04f-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
