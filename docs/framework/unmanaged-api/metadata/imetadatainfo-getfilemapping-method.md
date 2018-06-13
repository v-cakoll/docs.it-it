---
title: Metodo IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 562b6fcd015441ce5eb6b5f0ab7a4f361bb229c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449429"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="43db9-102">Metodo IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="43db9-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="43db9-103">Ottiene l'area di memoria del file mappato e il tipo di mapping.</span><span class="sxs-lookup"><span data-stu-id="43db9-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43db9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43db9-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43db9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43db9-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="43db9-106">[out] Un puntatore all'inizio del file mappato.</span><span class="sxs-lookup"><span data-stu-id="43db9-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="43db9-107">[out] Le dimensioni dell'area mappato.</span><span class="sxs-lookup"><span data-stu-id="43db9-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="43db9-108">Se `pdwMappingType` è `fmFlat`, si tratta della dimensione del file.</span><span class="sxs-lookup"><span data-stu-id="43db9-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="43db9-109">[out] Oggetto [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valore che indica il tipo di mapping.</span><span class="sxs-lookup"><span data-stu-id="43db9-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="43db9-110">Restituisce sempre l'implementazione corrente di common language runtime (CLR) `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="43db9-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="43db9-111">Altri valori sono riservati per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="43db9-111">Other values are reserved for future use.</span></span> <span data-ttu-id="43db9-112">Tuttavia, è necessario verificare sempre il valore restituito, perché possono essere abilitate nelle versioni future o service release di altri valori.</span><span class="sxs-lookup"><span data-stu-id="43db9-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43db9-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43db9-113">Return Value</span></span>  
  
|<span data-ttu-id="43db9-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43db9-114">HRESULT</span></span>|<span data-ttu-id="43db9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43db9-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="43db9-116">Tutti gli output vengono compilati.</span><span class="sxs-lookup"><span data-stu-id="43db9-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="43db9-117">NULL passato come un valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="43db9-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="43db9-118">L'implementazione di Common Language Runtime non può fornire informazioni sull'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="43db9-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="43db9-119">Questa situazione può verificarsi per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="43db9-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="43db9-120">-L'ambito dei metadati è stato aperto con il `ofWrite` o `ofCopyMemory` flag.</span><span class="sxs-lookup"><span data-stu-id="43db9-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="43db9-121">-L'ambito dei metadati è stato aperto senza il `ofReadOnly` flag.</span><span class="sxs-lookup"><span data-stu-id="43db9-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="43db9-122">-La [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metodo utilizzato per aprire solo la parte di metadati del file.</span><span class="sxs-lookup"><span data-stu-id="43db9-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="43db9-123">-Il file non è un file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="43db9-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="43db9-124">**Nota:** tali condizioni dipendono dall'implementazione CLR e venga potrebbero essere ridotte in versioni future di CLR.</span><span class="sxs-lookup"><span data-stu-id="43db9-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43db9-125">Note</span><span class="sxs-lookup"><span data-stu-id="43db9-125">Remarks</span></span>  
 <span data-ttu-id="43db9-126">La memoria che `ppvData` punta è valida solo fino a quando l'ambito dei metadati sottostante è aperto.</span><span class="sxs-lookup"><span data-stu-id="43db9-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="43db9-127">Affinché il metodo funzioni, quando si esegue il mapping i metadati di un file su disco in memoria chiamando la [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) metodo, è necessario specificare il `ofReadOnly` flag e non è necessario specificare il `ofWrite` o `ofCopyMemory` flag.</span><span class="sxs-lookup"><span data-stu-id="43db9-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="43db9-128">La scelta del tipo di mapping di file per ogni ambito è specifica per una determinata implementazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="43db9-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="43db9-129">Non può essere impostata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="43db9-129">It cannot be set by the user.</span></span> <span data-ttu-id="43db9-130">Restituisce sempre l'implementazione corrente di CLR `fmFlat` in `pdwMappingType`, ma si può cambiare nelle future versioni di CLR o nelle future versioni di servizio di una determinata versione.</span><span class="sxs-lookup"><span data-stu-id="43db9-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="43db9-131">Controllare sempre il valore restituito `pdwMappingType`, poiché saranno necessario diversi tipi di layout e offset diversi.</span><span class="sxs-lookup"><span data-stu-id="43db9-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="43db9-132">Non è possibile passare NULL per uno dei tre parametri.</span><span class="sxs-lookup"><span data-stu-id="43db9-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="43db9-133">Il metodo restituisce `E_INVALIDARG`, e nessuno degli output viene riempito.</span><span class="sxs-lookup"><span data-stu-id="43db9-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="43db9-134">Verrà ignorato il tipo di mapping o le dimensioni dell'area può comportare una chiusura anomala del programma.</span><span class="sxs-lookup"><span data-stu-id="43db9-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43db9-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43db9-135">Requirements</span></span>  
 <span data-ttu-id="43db9-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43db9-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43db9-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="43db9-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43db9-138">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="43db9-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43db9-139">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43db9-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43db9-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43db9-140">See Also</span></span>  
 [<span data-ttu-id="43db9-141">Interfaccia IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="43db9-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="43db9-142">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="43db9-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
