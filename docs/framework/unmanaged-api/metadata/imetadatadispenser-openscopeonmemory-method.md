---
title: Metodo IMetaDataDispenser::OpenScopeOnMemory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.OpenScopeOnMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c6cfc21a5aecfc043a7720959610210df1d15ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="2babc-102">Metodo IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="2babc-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="2babc-103">Verrà visualizzata un'area di memoria che contiene i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="2babc-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="2babc-104">Vale a dire, questo metodo apre un'area specificata di memoria in cui i dati esistenti viene trattati come metadati.</span><span class="sxs-lookup"><span data-stu-id="2babc-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2babc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2babc-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2babc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2babc-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="2babc-107">[in] Un puntatore che specifica l'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2babc-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="2babc-108">[in] Le dimensioni dell'area di memoria, in byte.</span><span class="sxs-lookup"><span data-stu-id="2babc-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="2babc-109">[in] Il valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) di apertura.</span><span class="sxs-lookup"><span data-stu-id="2babc-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="2babc-110">[in] L'IID dell'interfaccia di metadati desiderati da restituire. il chiamante utilizzerà l'interfaccia per l'importazione (lettura) o la creazione dei metadati (scrittura).</span><span class="sxs-lookup"><span data-stu-id="2babc-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="2babc-111">Il valore di `riid` deve specificare una delle interfacce "import" o "generazione".</span><span class="sxs-lookup"><span data-stu-id="2babc-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="2babc-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="2babc-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2babc-113">[out] Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="2babc-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2babc-114">Note</span><span class="sxs-lookup"><span data-stu-id="2babc-114">Remarks</span></span>  
 <span data-ttu-id="2babc-115">La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".</span><span class="sxs-lookup"><span data-stu-id="2babc-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="2babc-116">Il `OpenScopeOnMemory` è simile al metodo di [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) (metodo), ad eccezione del fatto che i metadati di interesse esistono già in memoria, piuttosto che in un file su disco.</span><span class="sxs-lookup"><span data-stu-id="2babc-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="2babc-117">Se l'area di destinazione di memoria non contiene metadati di common language runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2babc-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2babc-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2babc-118">Requirements</span></span>  
 <span data-ttu-id="2babc-119">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2babc-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2babc-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2babc-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2babc-121">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2babc-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2babc-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2babc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2babc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2babc-123">See Also</span></span>  
 [<span data-ttu-id="2babc-124">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="2babc-125">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="2babc-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2babc-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="2babc-127">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="2babc-128">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2babc-129">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2babc-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="2babc-130">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2babc-131">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2babc-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
