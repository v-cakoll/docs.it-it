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
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175928"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="e00d8-102">Metodo IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="e00d8-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="e00d8-103">Apre un'area di memoria che contiene metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="e00d8-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="e00d8-104">In altri luogo, questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="e00d8-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00d8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e00d8-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00d8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e00d8-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="e00d8-107">[in] Puntatore che specifica l'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="e00d8-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="e00d8-108">[in] Dimensione dell'area di memoria, in byte.</span><span class="sxs-lookup"><span data-stu-id="e00d8-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="e00d8-109">[in] Valore dell'enumerazione [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="e00d8-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="e00d8-110">[in] IID dell'interfaccia di metadati desiderata da restituire; il chiamante utilizzerà l'interfaccia per importare (leggere) o generare (scrivere) metadati.</span><span class="sxs-lookup"><span data-stu-id="e00d8-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="e00d8-111">Il valore `riid` di deve specificare una delle interfacce "import" o "emit".</span><span class="sxs-lookup"><span data-stu-id="e00d8-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="e00d8-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="e00d8-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="e00d8-113">[fuori] Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="e00d8-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e00d8-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e00d8-114">Remarks</span></span>  
 <span data-ttu-id="e00d8-115">La copia in memoria dei metadati può essere interrogata utilizzando metodi da una delle interfacce "import" o aggiunta all'utilizzo di metodi da una delle interfacce "emit".</span><span class="sxs-lookup"><span data-stu-id="e00d8-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="e00d8-116">Il `OpenScopeOnMemory` metodo è simile al metodo [IMetaDataDispenser::OpenScope,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) con la differenza che i metadati di interesse esistono già in memoria, anziché in un file su disco.</span><span class="sxs-lookup"><span data-stu-id="e00d8-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="e00d8-117">Se l'area di destinazione della memoria non contiene `OpenScopeOnMemory` metadati CLR (Common Language Runtime), il metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e00d8-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00d8-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e00d8-118">Requirements</span></span>  
 <span data-ttu-id="e00d8-119">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e00d8-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00d8-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e00d8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e00d8-121">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e00d8-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e00d8-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e00d8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00d8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00d8-123">See also</span></span>

- [<span data-ttu-id="e00d8-124">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="e00d8-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="e00d8-125">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="e00d8-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="e00d8-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="e00d8-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="e00d8-127">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="e00d8-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="e00d8-128">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e00d8-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e00d8-129">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e00d8-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="e00d8-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e00d8-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e00d8-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e00d8-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
