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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175265"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="156dd-102">Metodo IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="156dd-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="156dd-103">Ottiene l'area di memoria del file mappato e il tipo di mapping.</span><span class="sxs-lookup"><span data-stu-id="156dd-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="156dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="156dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="156dd-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="156dd-106">out Puntatore all'inizio del file mappato.</span><span class="sxs-lookup"><span data-stu-id="156dd-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="156dd-107">out Dimensioni dell'area mappata.</span><span class="sxs-lookup"><span data-stu-id="156dd-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="156dd-108">Se `pdwMappingType` è `fmFlat`, si tratta della dimensione del file.</span><span class="sxs-lookup"><span data-stu-id="156dd-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="156dd-109">out Valore [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) che indica il tipo di mapping.</span><span class="sxs-lookup"><span data-stu-id="156dd-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="156dd-110">L'implementazione corrente del Common Language Runtime (CLR) restituisce `fmFlat`sempre.</span><span class="sxs-lookup"><span data-stu-id="156dd-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="156dd-111">Altri valori sono riservati per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="156dd-111">Other values are reserved for future use.</span></span> <span data-ttu-id="156dd-112">Tuttavia, è sempre necessario verificare il valore restituito, perché gli altri valori possono essere abilitati nelle versioni future o nei rilasci del servizio.</span><span class="sxs-lookup"><span data-stu-id="156dd-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="156dd-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="156dd-113">Return Value</span></span>  
  
|<span data-ttu-id="156dd-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="156dd-114">HRESULT</span></span>|<span data-ttu-id="156dd-115">Description</span><span class="sxs-lookup"><span data-stu-id="156dd-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="156dd-116">Tutti gli output sono pieni.</span><span class="sxs-lookup"><span data-stu-id="156dd-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="156dd-117">NULL è stato passato come valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="156dd-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="156dd-118">L'implementazione CLR non è in grado di fornire informazioni sull'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="156dd-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="156dd-119">Ciò può verificarsi per i seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="156dd-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="156dd-120">-L'ambito dei metadati è stato aperto `ofWrite` con `ofCopyMemory` il flag o.</span><span class="sxs-lookup"><span data-stu-id="156dd-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="156dd-121">-L'ambito dei metadati è stato aperto `ofReadOnly` senza il flag.</span><span class="sxs-lookup"><span data-stu-id="156dd-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="156dd-122">-Il metodo [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) è stato usato per aprire solo la parte di metadati del file.</span><span class="sxs-lookup"><span data-stu-id="156dd-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="156dd-123">-Il file non è un file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="156dd-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="156dd-124">**Nota:**  Queste condizioni dipendono dall'implementazione di CLR e probabilmente verranno indebolite nelle versioni future di CLR.</span><span class="sxs-lookup"><span data-stu-id="156dd-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="156dd-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="156dd-125">Remarks</span></span>  
 <span data-ttu-id="156dd-126">La memoria a `ppvData` cui punta è valida solo fino a quando l'ambito dei metadati sottostante è aperto.</span><span class="sxs-lookup"><span data-stu-id="156dd-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="156dd-127">Per consentire il funzionamento di questo metodo, quando si esegue il mapping dei metadati di un file su disco in memoria chiamando il metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , è necessario specificare il `ofReadOnly` flag e non è necessario specificare il `ofWrite` flag `ofCopyMemory` o.</span><span class="sxs-lookup"><span data-stu-id="156dd-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="156dd-128">La scelta del tipo di mapping dei file per ogni ambito è specifica di una determinata implementazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="156dd-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="156dd-129">Non può essere impostata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="156dd-129">It cannot be set by the user.</span></span> <span data-ttu-id="156dd-130">L'implementazione corrente di CLR restituisce `fmFlat` sempre in `pdwMappingType`, ma può cambiare nelle versioni future di CLR o nelle versioni future del servizio di una determinata versione.</span><span class="sxs-lookup"><span data-stu-id="156dd-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="156dd-131">È consigliabile controllare sempre il valore restituito in `pdwMappingType`, perché tipi diversi avranno layout e offset diversi.</span><span class="sxs-lookup"><span data-stu-id="156dd-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="156dd-132">Il passaggio di un valore NULL per uno dei tre parametri non è supportato.</span><span class="sxs-lookup"><span data-stu-id="156dd-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="156dd-133">Il metodo restituisce `E_INVALIDARG`e nessuno degli output viene compilato.</span><span class="sxs-lookup"><span data-stu-id="156dd-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="156dd-134">Ignorando il tipo di mapping o la dimensione dell'area può verificarsi una chiusura anomala del programma.</span><span class="sxs-lookup"><span data-stu-id="156dd-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="156dd-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="156dd-135">Requirements</span></span>  
 <span data-ttu-id="156dd-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="156dd-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="156dd-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="156dd-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="156dd-138">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="156dd-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="156dd-139">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="156dd-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="156dd-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="156dd-140">See also</span></span>

- [<span data-ttu-id="156dd-141">Interfaccia IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="156dd-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="156dd-142">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="156dd-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
