---
title: Metodo IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 905de2745be085391bef8ea32b8f82a5da78f3a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681196"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="2cf74-102">Metodo IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="2cf74-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="2cf74-103">Apre un file esistente su disco e viene eseguito il mapping dei metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="2cf74-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cf74-104">Syntax</span></span>  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cf74-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="2cf74-106">[in] Il nome del file da aprire.</span><span class="sxs-lookup"><span data-stu-id="2cf74-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="2cf74-107">Il file deve contenere metadati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2cf74-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="2cf74-108">[in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="2cf74-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="2cf74-109">[in] IID dell'interfaccia di metadati desiderati da restituire. il chiamante Usa l'interfaccia per importare (lettura) o la creazione dei metadati (scrittura).</span><span class="sxs-lookup"><span data-stu-id="2cf74-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="2cf74-110">Il valore di `riid` deve specificare una delle interfacce "import" o "Crea".</span><span class="sxs-lookup"><span data-stu-id="2cf74-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="2cf74-111">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="2cf74-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2cf74-112">[out] Il puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="2cf74-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cf74-113">Note</span><span class="sxs-lookup"><span data-stu-id="2cf74-113">Remarks</span></span>  
 <span data-ttu-id="2cf74-114">La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".</span><span class="sxs-lookup"><span data-stu-id="2cf74-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="2cf74-115">Se il file di destinazione non contiene metadati CLR, il `OpenScope` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2cf74-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="2cf74-116">In .NET Framework versione 1.0 e 1.1, se un ambito viene aperto con `dwOpenFlags` impostata su ofRead, è idoneo per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="2cf74-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="2cf74-117">Vale a dire, se i successivi le chiamate a `OpenScope` passare il nome di un file che è stato precedentemente aperto, viene riutilizzato l'ambito esistente e non viene creato un nuovo set di strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="2cf74-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="2cf74-118">Tuttavia, possono verificarsi problemi a causa di questa condivisione.</span><span class="sxs-lookup"><span data-stu-id="2cf74-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="2cf74-119">In .NET Framework versione 2.0, gli ambiti di aperta con `dwOpenFlags` impostato su ofRead non sono più condivisi.</span><span class="sxs-lookup"><span data-stu-id="2cf74-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="2cf74-120">Usare il valore di ofReadOnly per consentire l'ambito da condividere.</span><span class="sxs-lookup"><span data-stu-id="2cf74-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="2cf74-121">Quando viene condiviso un ambito, le query che usano "lettura/scrittura" interfacce di metadati avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2cf74-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf74-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cf74-122">Requirements</span></span>  
 <span data-ttu-id="2cf74-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf74-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf74-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2cf74-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cf74-125">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2cf74-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2cf74-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf74-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf74-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cf74-127">See also</span></span>
- [<span data-ttu-id="2cf74-128">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="2cf74-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="2cf74-129">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="2cf74-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="2cf74-130">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2cf74-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="2cf74-131">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="2cf74-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="2cf74-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2cf74-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2cf74-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2cf74-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2cf74-134">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2cf74-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2cf74-135">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2cf74-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
