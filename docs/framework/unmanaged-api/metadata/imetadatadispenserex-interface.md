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
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008053"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="ce86d-102">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="ce86d-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="ce86d-103">Estende l'interfaccia dell' [interfaccia IMetaDataDispenser](imetadatadispenser-interface.md) per fornire la possibilità di controllare il funzionamento delle API dei metadati sull'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ce86d-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce86d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ce86d-104">Methods</span></span>  
  
|<span data-ttu-id="ce86d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ce86d-105">Method</span></span>|<span data-ttu-id="ce86d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce86d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce86d-107">Metodo FindAssembly</span><span class="sxs-lookup"><span data-stu-id="ce86d-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="ce86d-108">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="ce86d-108">This method is not implemented.</span></span> <span data-ttu-id="ce86d-109">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ce86d-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="ce86d-110">Metodo FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="ce86d-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="ce86d-111">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="ce86d-111">This method is not implemented.</span></span> <span data-ttu-id="ce86d-112">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ce86d-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="ce86d-113">Metodo GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="ce86d-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="ce86d-114">Ottiene la directory che include la Common Language Runtime corrente (CLR).</span><span class="sxs-lookup"><span data-stu-id="ce86d-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="ce86d-115">Questo metodo è supportato solo per l'utilizzo da debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="ce86d-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="ce86d-116">Se viene chiamato da un altro componente, restituirà E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ce86d-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="ce86d-117">Metodo GetOption</span><span class="sxs-lookup"><span data-stu-id="ce86d-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="ce86d-118">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ce86d-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="ce86d-119">L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ce86d-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="ce86d-120">Metodo OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="ce86d-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="ce86d-121">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="ce86d-121">This method is not implemented.</span></span> <span data-ttu-id="ce86d-122">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ce86d-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="ce86d-123">Metodo SetOption</span><span class="sxs-lookup"><span data-stu-id="ce86d-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="ce86d-124">Imposta l'opzione specificata su un valore specificato per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ce86d-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="ce86d-125">L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ce86d-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce86d-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce86d-126">Requirements</span></span>  
 <span data-ttu-id="ce86d-127">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce86d-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce86d-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce86d-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce86d-129">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ce86d-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce86d-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce86d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce86d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce86d-131">See also</span></span>

- [<span data-ttu-id="ce86d-132">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="ce86d-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="ce86d-133">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="ce86d-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="ce86d-134">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ce86d-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ce86d-135">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ce86d-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
