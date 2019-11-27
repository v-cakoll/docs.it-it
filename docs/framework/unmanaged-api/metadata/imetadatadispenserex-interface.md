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
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431141"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="bc279-102">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="bc279-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="bc279-103">Estende l'interfaccia dell' [interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) per fornire la possibilità di controllare il funzionamento delle API dei metadati sull'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="bc279-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc279-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bc279-104">Methods</span></span>  
  
|<span data-ttu-id="bc279-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bc279-105">Method</span></span>|<span data-ttu-id="bc279-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc279-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc279-107">Metodo FindAssembly</span><span class="sxs-lookup"><span data-stu-id="bc279-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="bc279-108">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="bc279-108">This method is not implemented.</span></span> <span data-ttu-id="bc279-109">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bc279-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="bc279-110">Metodo FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="bc279-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="bc279-111">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="bc279-111">This method is not implemented.</span></span> <span data-ttu-id="bc279-112">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bc279-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="bc279-113">Metodo GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="bc279-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="bc279-114">Ottiene la directory che include la Common Language Runtime corrente (CLR).</span><span class="sxs-lookup"><span data-stu-id="bc279-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="bc279-115">Questo metodo è supportato solo per l'utilizzo da debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="bc279-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="bc279-116">Se viene chiamato da un altro componente, restituirà E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bc279-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="bc279-117">Metodo GetOption</span><span class="sxs-lookup"><span data-stu-id="bc279-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="bc279-118">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="bc279-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="bc279-119">L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="bc279-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="bc279-120">Metodo OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="bc279-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="bc279-121">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="bc279-121">This method is not implemented.</span></span> <span data-ttu-id="bc279-122">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bc279-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="bc279-123">Metodo SetOption</span><span class="sxs-lookup"><span data-stu-id="bc279-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="bc279-124">Imposta l'opzione specificata su un valore specificato per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="bc279-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="bc279-125">L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="bc279-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc279-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc279-126">Requirements</span></span>  
 <span data-ttu-id="bc279-127">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc279-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc279-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bc279-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc279-129">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bc279-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc279-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc279-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc279-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc279-131">See also</span></span>

- [<span data-ttu-id="bc279-132">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="bc279-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="bc279-133">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="bc279-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="bc279-134">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bc279-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bc279-135">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bc279-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
