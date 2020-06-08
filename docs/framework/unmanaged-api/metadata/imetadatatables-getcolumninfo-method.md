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
ms.openlocfilehash: a044924810016eea60682b8765aeee448b552f0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501196"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="d54fe-102">Metodo IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="d54fe-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="d54fe-103">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="d54fe-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d54fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d54fe-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d54fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d54fe-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="d54fe-106">in Indice della tabella desiderata.</span><span class="sxs-lookup"><span data-stu-id="d54fe-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="d54fe-107">in Indice della colonna desiderata.</span><span class="sxs-lookup"><span data-stu-id="d54fe-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="d54fe-108">out Puntatore all'offset della colonna nella riga.</span><span class="sxs-lookup"><span data-stu-id="d54fe-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="d54fe-109">out Puntatore alla dimensione, in byte, della colonna.</span><span class="sxs-lookup"><span data-stu-id="d54fe-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="d54fe-110">out Puntatore al tipo dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="d54fe-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d54fe-111">out Puntatore a un puntatore al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="d54fe-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="d54fe-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d54fe-112">Remarks</span></span>

<span data-ttu-id="d54fe-113">Il tipo di colonna restituito rientra in un intervallo di valori:</span><span class="sxs-lookup"><span data-stu-id="d54fe-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="d54fe-114">pType</span><span class="sxs-lookup"><span data-stu-id="d54fe-114">pType</span></span>                    | <span data-ttu-id="d54fe-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d54fe-115">Description</span></span>   | <span data-ttu-id="d54fe-116">Funzione helper</span><span class="sxs-lookup"><span data-stu-id="d54fe-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="d54fe-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="d54fe-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="d54fe-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="d54fe-118">(0..63)</span></span>   | <span data-ttu-id="d54fe-119">Sbarazzarsi</span><span class="sxs-lookup"><span data-stu-id="d54fe-119">Rid</span></span>           | <span data-ttu-id="d54fe-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-120">**IsRidType**</span></span><br><span data-ttu-id="d54fe-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="d54fe-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="d54fe-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="d54fe-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="d54fe-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="d54fe-123">(64..95)</span></span> | <span data-ttu-id="d54fe-124">Token codificato</span><span class="sxs-lookup"><span data-stu-id="d54fe-124">Coded token</span></span> | <span data-ttu-id="d54fe-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="d54fe-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="d54fe-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="d54fe-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="d54fe-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="d54fe-128">Int16</span><span class="sxs-lookup"><span data-stu-id="d54fe-128">Int16</span></span>         | <span data-ttu-id="d54fe-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="d54fe-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="d54fe-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="d54fe-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="d54fe-131">UInt16</span></span>        | <span data-ttu-id="d54fe-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="d54fe-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="d54fe-133">`iLONG` (98)</span></span>             | <span data-ttu-id="d54fe-134">Int32</span><span class="sxs-lookup"><span data-stu-id="d54fe-134">Int32</span></span>         | <span data-ttu-id="d54fe-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="d54fe-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="d54fe-136">`iULONG` (99)</span></span>            | <span data-ttu-id="d54fe-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="d54fe-137">UInt32</span></span>        | <span data-ttu-id="d54fe-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="d54fe-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="d54fe-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="d54fe-140">Byte</span><span class="sxs-lookup"><span data-stu-id="d54fe-140">Byte</span></span>          | <span data-ttu-id="d54fe-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="d54fe-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="d54fe-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="d54fe-143">string</span><span class="sxs-lookup"><span data-stu-id="d54fe-143">String</span></span>        | <span data-ttu-id="d54fe-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="d54fe-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="d54fe-145">`iGUID` (102)</span></span>            | <span data-ttu-id="d54fe-146">Guid</span><span class="sxs-lookup"><span data-stu-id="d54fe-146">Guid</span></span>          | <span data-ttu-id="d54fe-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="d54fe-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="d54fe-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="d54fe-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="d54fe-149">Blob</span></span>          | <span data-ttu-id="d54fe-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="d54fe-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="d54fe-151">I valori archiviati nell' *heap* , ovvero, `IsHeapType == true` possono essere letti utilizzando:</span><span class="sxs-lookup"><span data-stu-id="d54fe-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="d54fe-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="d54fe-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="d54fe-153">`iGUID`: **IMetadataTables. GETguid**</span><span class="sxs-lookup"><span data-stu-id="d54fe-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="d54fe-154">`iBLOB`: **IMetadataTables. GetBlob**</span><span class="sxs-lookup"><span data-stu-id="d54fe-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d54fe-155">Per usare le costanti definite nella tabella precedente, includere la direttiva `#define _DEFINE_META_DATA_META_CONSTANTS` fornita dal file di intestazione *cor. h* .</span><span class="sxs-lookup"><span data-stu-id="d54fe-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="d54fe-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d54fe-156">Requirements</span></span>  
 <span data-ttu-id="d54fe-157">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d54fe-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d54fe-158">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d54fe-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d54fe-159">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d54fe-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d54fe-160">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d54fe-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54fe-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d54fe-161">See also</span></span>

- [<span data-ttu-id="d54fe-162">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d54fe-162">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d54fe-163">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d54fe-163">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
