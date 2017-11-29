---
title: Metodo IMetaDataDispenser::OpenScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.OpenScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09c057f42bb849b89d78d2d32af6637640ad22ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="eacd8-102">Metodo IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="eacd8-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="eacd8-103">Apre un file esistente, su disco e viene eseguito il mapping dei metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="eacd8-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eacd8-104">Syntax</span></span>  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eacd8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eacd8-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="eacd8-106">[in] Il nome del file da aprire.</span><span class="sxs-lookup"><span data-stu-id="eacd8-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="eacd8-107">Il file deve contenere metadati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="eacd8-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="eacd8-108">[in] Il valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) di apertura.</span><span class="sxs-lookup"><span data-stu-id="eacd8-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="eacd8-109">[in] L'IID dell'interfaccia di metadati desiderati da restituire. il chiamante utilizzerà l'interfaccia per l'importazione (lettura) o la creazione dei metadati (scrittura).</span><span class="sxs-lookup"><span data-stu-id="eacd8-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="eacd8-110">Il valore di `riid` deve specificare una delle interfacce "import" o "generazione".</span><span class="sxs-lookup"><span data-stu-id="eacd8-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="eacd8-111">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="eacd8-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="eacd8-112">[out] Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="eacd8-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eacd8-113">Note</span><span class="sxs-lookup"><span data-stu-id="eacd8-113">Remarks</span></span>  
 <span data-ttu-id="eacd8-114">La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".</span><span class="sxs-lookup"><span data-stu-id="eacd8-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="eacd8-115">Se il file di destinazione non contiene metadati CLR, la `OpenScope` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="eacd8-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="eacd8-116">In .NET Framework versione 1.0 e 1.1, se un ambito viene aperto con `dwOpenFlags` impostato su ofRead, è idoneo per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="eacd8-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="eacd8-117">Vale a dire se successive chiamate a `OpenScope` passare il nome di un file che è stato precedentemente aperto, l'ambito esistente viene riutilizzato e non viene creato un nuovo insieme di strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="eacd8-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="eacd8-118">Tuttavia, possono verificarsi problemi a causa di questa condivisione.</span><span class="sxs-lookup"><span data-stu-id="eacd8-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="eacd8-119">In .NET Framework versione 2.0, gli ambiti di aperta con `dwOpenFlags` impostato su ofRead non sono più condivisi.</span><span class="sxs-lookup"><span data-stu-id="eacd8-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="eacd8-120">Utilizzare il valore ofReadOnly per consentire l'ambito per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="eacd8-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="eacd8-121">Quando si condivide un ambito, le query che utilizzano "lettura/scrittura" interfacce di metadati avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="eacd8-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eacd8-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eacd8-122">Requirements</span></span>  
 <span data-ttu-id="eacd8-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eacd8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eacd8-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eacd8-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eacd8-125">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eacd8-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eacd8-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eacd8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacd8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eacd8-127">See Also</span></span>  
 [<span data-ttu-id="eacd8-128">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="eacd8-129">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="eacd8-130">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="eacd8-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="eacd8-131">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="eacd8-132">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="eacd8-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="eacd8-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="eacd8-134">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="eacd8-135">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eacd8-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
