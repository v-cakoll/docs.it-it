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
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442319"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="dc854-102">Metodo IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="dc854-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="dc854-103">Apre un'area di memoria contenente i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="dc854-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="dc854-104">Questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="dc854-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc854-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc854-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc854-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc854-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="dc854-107">in Puntatore che specifica l'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="dc854-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="dc854-108">in Dimensioni in byte dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="dc854-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="dc854-109">in Valore dell'enumerazione [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="dc854-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="dc854-110">in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per importare (leggere) o creare (scrivere) metadati.</span><span class="sxs-lookup"><span data-stu-id="dc854-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="dc854-111">Il valore di `riid` deve specificare una delle interfacce "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="dc854-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="dc854-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="dc854-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="dc854-113">out Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="dc854-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc854-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc854-114">Remarks</span></span>  
 <span data-ttu-id="dc854-115">La copia in memoria dei metadati può essere sottoposta a query usando i metodi di una delle interfacce di "importazione" oppure aggiunti a usando i metodi di una delle interfacce "Emit".</span><span class="sxs-lookup"><span data-stu-id="dc854-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="dc854-116">Il metodo `OpenScopeOnMemory` è simile al metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , ad eccezione del fatto che i metadati di interesse sono già presenti in memoria, anziché in un file su disco.</span><span class="sxs-lookup"><span data-stu-id="dc854-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="dc854-117">Se l'area di destinazione della memoria non contiene metadati Common Language Runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="dc854-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc854-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc854-118">Requirements</span></span>  
 <span data-ttu-id="dc854-119">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc854-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc854-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc854-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc854-121">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc854-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc854-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc854-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc854-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc854-123">See also</span></span>

- [<span data-ttu-id="dc854-124">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="dc854-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="dc854-125">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="dc854-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="dc854-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="dc854-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="dc854-127">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="dc854-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="dc854-128">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="dc854-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dc854-129">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="dc854-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="dc854-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="dc854-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dc854-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="dc854-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
