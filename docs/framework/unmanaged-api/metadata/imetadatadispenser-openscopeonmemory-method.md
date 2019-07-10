---
title: Metodo IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204e5660e95434f8d0c44d54f4fdbb1c2acc1e5d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777778"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="199a1-102">Metodo IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="199a1-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="199a1-103">Apre un'area di memoria che contiene i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="199a1-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="199a1-104">Vale a dire, questo metodo consente di aprire un'area specificata di memoria in cui i dati esistenti viene considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="199a1-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199a1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="199a1-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="199a1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="199a1-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="199a1-107">[in] Un puntatore che specifica l'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="199a1-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="199a1-108">[in] Le dimensioni dell'area di memoria, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="199a1-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="199a1-109">[in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="199a1-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="199a1-110">[in] IID dell'interfaccia di metadati desiderati da restituire. il chiamante Usa l'interfaccia per importare (lettura) o la creazione dei metadati (scrittura).</span><span class="sxs-lookup"><span data-stu-id="199a1-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="199a1-111">Il valore di `riid` deve specificare una delle interfacce "import" o "Crea".</span><span class="sxs-lookup"><span data-stu-id="199a1-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="199a1-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="199a1-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="199a1-113">[out] Il puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="199a1-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="199a1-114">Note</span><span class="sxs-lookup"><span data-stu-id="199a1-114">Remarks</span></span>  
 <span data-ttu-id="199a1-115">La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".</span><span class="sxs-lookup"><span data-stu-id="199a1-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="199a1-116">Il `OpenScopeOnMemory` metodo è simile al [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) metodo, ad eccezione del fatto che i metadati di interesse esistono già in memoria, anziché in un file su disco.</span><span class="sxs-lookup"><span data-stu-id="199a1-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="199a1-117">Se l'area di destinazione di memoria non contiene metadati di common language runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="199a1-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="199a1-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="199a1-118">Requirements</span></span>  
 <span data-ttu-id="199a1-119">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199a1-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="199a1-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="199a1-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="199a1-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="199a1-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="199a1-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="199a1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199a1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="199a1-123">See also</span></span>

- [<span data-ttu-id="199a1-124">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="199a1-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="199a1-125">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="199a1-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="199a1-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="199a1-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="199a1-127">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="199a1-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="199a1-128">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="199a1-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="199a1-129">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="199a1-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="199a1-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="199a1-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="199a1-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="199a1-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
