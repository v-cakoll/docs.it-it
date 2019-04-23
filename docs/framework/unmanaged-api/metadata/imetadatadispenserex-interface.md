---
title: Interfaccia IMetaDataDispenserEx
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96475086b1244ae75ed692dd10cb693af0be9af7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186953"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="da94e-102">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="da94e-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="da94e-103">Estende la [interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaccia per fornire la possibilità di controllare come l'API dei metadati in ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="da94e-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da94e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="da94e-104">Methods</span></span>  
  
|<span data-ttu-id="da94e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="da94e-105">Method</span></span>|<span data-ttu-id="da94e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da94e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da94e-107">Metodo FindAssembly</span><span class="sxs-lookup"><span data-stu-id="da94e-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="da94e-108">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="da94e-108">This method is not implemented.</span></span> <span data-ttu-id="da94e-109">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da94e-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="da94e-110">Metodo FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="da94e-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="da94e-111">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="da94e-111">This method is not implemented.</span></span> <span data-ttu-id="da94e-112">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da94e-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="da94e-113">Metodo GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="da94e-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="da94e-114">Ottiene la directory che contiene corrente common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="da94e-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="da94e-115">Questo metodo è supportato solo per uso dai debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="da94e-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="da94e-116">Se chiamato da un altro componente, verrà restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da94e-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="da94e-117">Metodo GetOption</span><span class="sxs-lookup"><span data-stu-id="da94e-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="da94e-118">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="da94e-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="da94e-119">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="da94e-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="da94e-120">Metodo OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="da94e-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="da94e-121">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="da94e-121">This method is not implemented.</span></span> <span data-ttu-id="da94e-122">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da94e-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="da94e-123">Metodo SetOption</span><span class="sxs-lookup"><span data-stu-id="da94e-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="da94e-124">Imposta l'opzione specificata in un determinato valore per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="da94e-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="da94e-125">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="da94e-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da94e-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da94e-126">Requirements</span></span>  
 <span data-ttu-id="da94e-127">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da94e-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da94e-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="da94e-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da94e-129">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="da94e-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da94e-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da94e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da94e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da94e-131">See also</span></span>

- [<span data-ttu-id="da94e-132">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="da94e-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="da94e-133">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="da94e-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="da94e-134">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="da94e-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="da94e-135">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="da94e-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
