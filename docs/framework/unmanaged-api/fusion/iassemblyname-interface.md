---
title: Interfaccia IAssemblyName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="1710f-102">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="1710f-102">IAssemblyName Interface</span></span>
<span data-ttu-id="1710f-103">Fornisce metodi per la descrizione e l'utilizzo di un'identità univoca di assembly.</span><span class="sxs-lookup"><span data-stu-id="1710f-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1710f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1710f-104">Methods</span></span>  
  
|<span data-ttu-id="1710f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1710f-105">Method</span></span>|<span data-ttu-id="1710f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1710f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1710f-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="1710f-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="1710f-108">Crea una copia superficiale di questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1710f-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="1710f-109">Metodo Finalize</span><span class="sxs-lookup"><span data-stu-id="1710f-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="1710f-110">Questo consente `IAssemblyName` oggetto per rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il distruttore.</span><span class="sxs-lookup"><span data-stu-id="1710f-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="1710f-111">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="1710f-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="1710f-112">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1710f-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="1710f-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="1710f-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="1710f-114">Ottiene il nome semplice non crittografato dell'assembly a cui fa riferimento questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1710f-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="1710f-115">Metodo GetProperty</span><span class="sxs-lookup"><span data-stu-id="1710f-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="1710f-116">Ottiene un puntatore alla proprietà a cui fa riferimento specificato `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="1710f-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="1710f-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="1710f-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="1710f-118">Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1710f-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="1710f-119">Metodo IsEqual</span><span class="sxs-lookup"><span data-stu-id="1710f-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="1710f-120">Determina se un oggetto `IAssemblyName` è uguale all'oggetto `IAssemblyName`, in base ai flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="1710f-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="1710f-121">Metodo SetProperty</span><span class="sxs-lookup"><span data-stu-id="1710f-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="1710f-122">Imposta il valore della proprietà a cui fa riferimento specificato `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="1710f-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1710f-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1710f-123">Requirements</span></span>  
 <span data-ttu-id="1710f-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1710f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1710f-125">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1710f-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1710f-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1710f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1710f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1710f-127">See Also</span></span>  
 [<span data-ttu-id="1710f-128">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="1710f-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="1710f-129">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="1710f-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
