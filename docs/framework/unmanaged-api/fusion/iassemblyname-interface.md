---
title: Interfaccia IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22276e543e8eeb9c6cf9aeee7a9af92c503d3a7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549015"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="e1bed-102">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="e1bed-102">IAssemblyName Interface</span></span>
<span data-ttu-id="e1bed-103">Fornisce metodi per la descrizione e l'utilizzo di identità univoca di un assembly.</span><span class="sxs-lookup"><span data-stu-id="e1bed-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1bed-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e1bed-104">Methods</span></span>  
  
|<span data-ttu-id="e1bed-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e1bed-105">Method</span></span>|<span data-ttu-id="e1bed-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1bed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1bed-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="e1bed-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="e1bed-108">Crea una copia superficiale dell'oggetto `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e1bed-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="e1bed-109">Metodo Finalize</span><span class="sxs-lookup"><span data-stu-id="e1bed-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="e1bed-110">Consente questo `IAssemblyName` oggetto rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.</span><span class="sxs-lookup"><span data-stu-id="e1bed-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="e1bed-111">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1bed-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="e1bed-112">Ottiene il nome leggibile dell'assembly a cui fa riferimento `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e1bed-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="e1bed-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="e1bed-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="e1bed-114">Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e1bed-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="e1bed-115">Metodo GetProperty</span><span class="sxs-lookup"><span data-stu-id="e1bed-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="e1bed-116">Ottiene un puntatore per la proprietà fa riferimento l'oggetto specificato `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="e1bed-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="e1bed-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="e1bed-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="e1bed-118">Ottiene le informazioni sulla versione per l'assembly fa riferimento questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e1bed-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="e1bed-119">Metodo IsEqual</span><span class="sxs-lookup"><span data-stu-id="e1bed-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="e1bed-120">Determina se un oggetto specificato `IAssemblyName` è uguale all'oggetto `IAssemblyName`, in base al flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="e1bed-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="e1bed-121">Metodo SetProperty</span><span class="sxs-lookup"><span data-stu-id="e1bed-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="e1bed-122">Imposta il valore della proprietà specificato fa riferimento `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="e1bed-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1bed-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1bed-123">Requirements</span></span>  
 <span data-ttu-id="e1bed-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1bed-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1bed-125">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e1bed-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e1bed-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1bed-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bed-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1bed-127">See also</span></span>
- [<span data-ttu-id="e1bed-128">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="e1bed-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="e1bed-129">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e1bed-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
