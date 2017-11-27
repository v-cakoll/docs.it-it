---
title: Metodo IMetaDataDispenser::DefineScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.DefineScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 964e6df1b6aba7ca85b627cf19c38f5df600b6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="f5b3c-102">Metodo IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="f5b3c-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="f5b3c-103">Crea una nuova area in memoria in cui è possibile creare nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5b3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5b3c-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5b3c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5b3c-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="f5b3c-106">[in] Il CLSID della versione di strutture di metadati da creare.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="f5b3c-107">Questo valore deve essere CLSID_CorMetaDataRuntime per .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="f5b3c-108">[in] Flag che specificano le opzioni.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-108">[in] Flags that specify options.</span></span> <span data-ttu-id="f5b3c-109">Questo valore deve essere zero per .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="f5b3c-110">[in] L'IID dell'interfaccia di metadati desiderati da restituire. il chiamante utilizzerà l'interfaccia per creare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="f5b3c-111">Il valore di `riid` deve specificare una delle interfacce di "generazione".</span><span class="sxs-lookup"><span data-stu-id="f5b3c-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="f5b3c-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit e IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f5b3c-113">[out] Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5b3c-114">Note</span><span class="sxs-lookup"><span data-stu-id="f5b3c-114">Remarks</span></span>  
 <span data-ttu-id="f5b3c-115">`DefineScope`Crea un set di tabelle di metadati in memoria, genera un GUID (identificatore di versione del modulo o MVID) per i metadati e viene creata una voce nella tabella dei moduli per l'unità di compilazione generata.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="f5b3c-116">È possibile collegare gli attributi per l'ambito dei metadati nel suo complesso usando il [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) metodo, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="f5b3c-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5b3c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5b3c-117">Requirements</span></span>  
 <span data-ttu-id="f5b3c-118">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5b3c-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5b3c-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f5b3c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5b3c-120">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5b3c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5b3c-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5b3c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b3c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5b3c-122">See Also</span></span>  
 [<span data-ttu-id="f5b3c-123">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="f5b3c-124">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="f5b3c-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f5b3c-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="f5b3c-126">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f5b3c-127">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f5b3c-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
