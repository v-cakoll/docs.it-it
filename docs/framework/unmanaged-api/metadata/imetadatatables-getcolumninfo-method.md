---
title: Metodo IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177126"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="404ef-102">Metodo IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="404ef-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="404ef-103">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="404ef-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="404ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="404ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="404ef-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="404ef-106">[in] Indice della tabella desiderata.</span><span class="sxs-lookup"><span data-stu-id="404ef-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="404ef-107">[in] Indice della colonna desiderata.</span><span class="sxs-lookup"><span data-stu-id="404ef-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="404ef-108">[fuori] Puntatore all'offset della colonna nella riga.</span><span class="sxs-lookup"><span data-stu-id="404ef-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="404ef-109">[fuori] Puntatore alla dimensione, in byte, della colonna.</span><span class="sxs-lookup"><span data-stu-id="404ef-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="404ef-110">[fuori] Puntatore al tipo di valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="404ef-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="404ef-111">[fuori] Puntatore a un puntatore al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="404ef-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="404ef-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="404ef-112">Remarks</span></span>

<span data-ttu-id="404ef-113">Il tipo di colonna restituito rientra in un intervallo di valori:The returned column type falls within a range of values:</span><span class="sxs-lookup"><span data-stu-id="404ef-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="404ef-114">pTipo</span><span class="sxs-lookup"><span data-stu-id="404ef-114">pType</span></span>                    | <span data-ttu-id="404ef-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="404ef-115">Description</span></span>   | <span data-ttu-id="404ef-116">Funzione di supporto</span><span class="sxs-lookup"><span data-stu-id="404ef-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="404ef-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="404ef-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="404ef-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="404ef-118">(0..63)</span></span>   | <span data-ttu-id="404ef-119">liberarsi</span><span class="sxs-lookup"><span data-stu-id="404ef-119">Rid</span></span>           | <span data-ttu-id="404ef-120">**IsRidType (tipo in stato di diridtype**</span><span class="sxs-lookup"><span data-stu-id="404ef-120">**IsRidType**</span></span><br><span data-ttu-id="404ef-121">**Token IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="404ef-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="404ef-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="404ef-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="404ef-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="404ef-123">(64..95)</span></span> | <span data-ttu-id="404ef-124">Token codificato</span><span class="sxs-lookup"><span data-stu-id="404ef-124">Coded token</span></span> | <span data-ttu-id="404ef-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="404ef-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="404ef-126">**Token IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="404ef-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="404ef-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="404ef-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="404ef-128">Int16</span><span class="sxs-lookup"><span data-stu-id="404ef-128">Int16</span></span>         | <span data-ttu-id="404ef-129">**IsFixedType (Tipo di oggetto)**</span><span class="sxs-lookup"><span data-stu-id="404ef-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="404ef-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="404ef-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="404ef-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="404ef-131">UInt16</span></span>        | <span data-ttu-id="404ef-132">**IsFixedType (Tipo di oggetto)**</span><span class="sxs-lookup"><span data-stu-id="404ef-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="404ef-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="404ef-133">`iLONG` (98)</span></span>             | <span data-ttu-id="404ef-134">Int32</span><span class="sxs-lookup"><span data-stu-id="404ef-134">Int32</span></span>         | <span data-ttu-id="404ef-135">**IsFixedType (Tipo di oggetto)**</span><span class="sxs-lookup"><span data-stu-id="404ef-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="404ef-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="404ef-136">`iULONG` (99)</span></span>            | <span data-ttu-id="404ef-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="404ef-137">UInt32</span></span>        | <span data-ttu-id="404ef-138">**IsFixedType (Tipo di oggetto)**</span><span class="sxs-lookup"><span data-stu-id="404ef-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="404ef-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="404ef-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="404ef-140">Byte</span><span class="sxs-lookup"><span data-stu-id="404ef-140">Byte</span></span>          | <span data-ttu-id="404ef-141">**IsFixedType (Tipo di oggetto)**</span><span class="sxs-lookup"><span data-stu-id="404ef-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="404ef-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="404ef-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="404ef-143">string</span><span class="sxs-lookup"><span data-stu-id="404ef-143">String</span></span>        | <span data-ttu-id="404ef-144">**IsHeapType (Tipo IsHeap)**</span><span class="sxs-lookup"><span data-stu-id="404ef-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="404ef-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="404ef-145">`iGUID` (102)</span></span>            | <span data-ttu-id="404ef-146">Guid</span><span class="sxs-lookup"><span data-stu-id="404ef-146">Guid</span></span>          | <span data-ttu-id="404ef-147">**IsHeapType (Tipo IsHeap)**</span><span class="sxs-lookup"><span data-stu-id="404ef-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="404ef-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="404ef-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="404ef-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="404ef-149">Blob</span></span>          | <span data-ttu-id="404ef-150">**IsHeapType (Tipo IsHeap)**</span><span class="sxs-lookup"><span data-stu-id="404ef-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="404ef-151">I valori archiviati nell'heap, `IsHeapType == true`ovvero , possono essere letti utilizzando: *heap*</span><span class="sxs-lookup"><span data-stu-id="404ef-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="404ef-152">`iSTRING`: **IMetadataTables.GetString**</span><span class="sxs-lookup"><span data-stu-id="404ef-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="404ef-153">`iGUID`: **IMetadataTables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="404ef-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="404ef-154">`iBLOB`: **IMetadataTables.GetBlob**</span><span class="sxs-lookup"><span data-stu-id="404ef-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="404ef-155">Per utilizzare le costanti definite nella tabella `#define _DEFINE_META_DATA_META_CONSTANTS` precedente, includere la direttiva fornita dal file di intestazione *cor.h.*</span><span class="sxs-lookup"><span data-stu-id="404ef-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="404ef-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="404ef-156">Requirements</span></span>  
 <span data-ttu-id="404ef-157">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404ef-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404ef-158">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="404ef-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="404ef-159">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="404ef-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="404ef-160">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404ef-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404ef-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="404ef-161">See also</span></span>

- [<span data-ttu-id="404ef-162">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="404ef-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="404ef-163">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="404ef-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
