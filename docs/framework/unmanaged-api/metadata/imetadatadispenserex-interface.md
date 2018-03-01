---
title: Interfaccia IMetaDataDispenserEx
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
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4cf062029647d4834118a459db378c8535182daf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="49b98-102">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="49b98-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="49b98-103">Estende il [interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaccia per fornire la funzionalità di controllo come API dei metadati sull'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49b98-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49b98-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49b98-104">Methods</span></span>  
  
|<span data-ttu-id="49b98-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49b98-105">Method</span></span>|<span data-ttu-id="49b98-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49b98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49b98-107">Metodo FindAssembly</span><span class="sxs-lookup"><span data-stu-id="49b98-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="49b98-108">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="49b98-108">This method is not implemented.</span></span> <span data-ttu-id="49b98-109">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49b98-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="49b98-110">Metodo FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="49b98-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="49b98-111">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="49b98-111">This method is not implemented.</span></span> <span data-ttu-id="49b98-112">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49b98-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="49b98-113">Metodo GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="49b98-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="49b98-114">Ottiene la directory contenente corrente common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="49b98-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="49b98-115">Questo metodo è supportato solo per uso dai debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="49b98-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="49b98-116">Se chiamato da un altro componente, verrà restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49b98-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="49b98-117">Metodo GetOption</span><span class="sxs-lookup"><span data-stu-id="49b98-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="49b98-118">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49b98-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="49b98-119">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49b98-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="49b98-120">Metodo OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="49b98-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="49b98-121">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="49b98-121">This method is not implemented.</span></span> <span data-ttu-id="49b98-122">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49b98-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="49b98-123">Metodo SetOption</span><span class="sxs-lookup"><span data-stu-id="49b98-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="49b98-124">Imposta l'opzione specificata per un determinato valore per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49b98-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="49b98-125">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49b98-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49b98-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49b98-126">Requirements</span></span>  
 <span data-ttu-id="49b98-127">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b98-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b98-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49b98-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49b98-129">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49b98-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49b98-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b98-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b98-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49b98-131">See Also</span></span>  
 [<span data-ttu-id="49b98-132">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="49b98-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="49b98-133">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="49b98-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="49b98-134">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="49b98-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="49b98-135">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="49b98-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
