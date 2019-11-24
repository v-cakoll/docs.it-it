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
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="f600c-102">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f600c-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="f600c-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="f600c-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f600c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f600c-104">Methods</span></span>  
  
|<span data-ttu-id="f600c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f600c-105">Method</span></span>|<span data-ttu-id="f600c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f600c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f600c-107">Metodo FindAssembly</span><span class="sxs-lookup"><span data-stu-id="f600c-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="f600c-108">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="f600c-108">This method is not implemented.</span></span> <span data-ttu-id="f600c-109">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f600c-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="f600c-110">Metodo FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="f600c-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="f600c-111">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="f600c-111">This method is not implemented.</span></span> <span data-ttu-id="f600c-112">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f600c-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="f600c-113">Metodo GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="f600c-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="f600c-114">Gets the directory that holds the current common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f600c-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="f600c-115">This method is supported only for use by out-of-process debuggers.</span><span class="sxs-lookup"><span data-stu-id="f600c-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="f600c-116">If called from another component, it will return E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f600c-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="f600c-117">Metodo GetOption</span><span class="sxs-lookup"><span data-stu-id="f600c-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="f600c-118">Gets the value of the specified option for the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="f600c-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="f600c-119">The option controls how calls to the current metadata scope are handled.</span><span class="sxs-lookup"><span data-stu-id="f600c-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="f600c-120">Metodo OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="f600c-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="f600c-121">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="f600c-121">This method is not implemented.</span></span> <span data-ttu-id="f600c-122">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f600c-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="f600c-123">Metodo SetOption</span><span class="sxs-lookup"><span data-stu-id="f600c-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="f600c-124">Sets the specified option to a given value for the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="f600c-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="f600c-125">The option controls how calls to the current metadata scope are handled.</span><span class="sxs-lookup"><span data-stu-id="f600c-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f600c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f600c-126">Requirements</span></span>  
 <span data-ttu-id="f600c-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f600c-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f600c-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f600c-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f600c-129">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f600c-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f600c-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f600c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f600c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f600c-131">See also</span></span>

- [<span data-ttu-id="f600c-132">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="f600c-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="f600c-133">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="f600c-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="f600c-134">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f600c-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f600c-135">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f600c-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
