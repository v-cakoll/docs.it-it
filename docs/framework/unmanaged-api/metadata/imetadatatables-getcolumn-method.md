---
title: Metodo IMetaDataTables::GetColumn
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177132"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="925f4-102">Metodo IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="925f4-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="925f4-103">Ottiene un puntatore al valore contenuto nella cella della colonna e della riga specificate nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="925f4-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="925f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="925f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="925f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="925f4-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="925f4-106">[in] Indice della tabella.</span><span class="sxs-lookup"><span data-stu-id="925f4-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="925f4-107">[in] Indice della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="925f4-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="925f4-108">[in] Indice della riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="925f4-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="925f4-109">[fuori] Puntatore al valore nella cella.</span><span class="sxs-lookup"><span data-stu-id="925f4-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="925f4-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="925f4-110">Remarks</span></span>

<span data-ttu-id="925f4-111">L'interpretazione del valore restituito `pVal` attraverso dipende dal tipo della colonna.</span><span class="sxs-lookup"><span data-stu-id="925f4-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="925f4-112">Il tipo di colonna può essere determinato chiamando [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="925f4-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="925f4-113">Il **GetColumn** metodo converte automaticamente le colonne di tipo **Rid** o **CodedToken** in valori a 32 bit `mdToken` completi.</span><span class="sxs-lookup"><span data-stu-id="925f4-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="925f4-114">Converte inoltre automaticamente valori a 8 o 16 bit in valori a 32 bit completi.</span><span class="sxs-lookup"><span data-stu-id="925f4-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="925f4-115">Per le colonne di tipo *heap,* il *pVal* restituito sarà un indice nell'heap corrispondente.</span><span class="sxs-lookup"><span data-stu-id="925f4-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="925f4-116">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="925f4-116">Column type</span></span>              | <span data-ttu-id="925f4-117">pVal contiene</span><span class="sxs-lookup"><span data-stu-id="925f4-117">pVal contains</span></span> | <span data-ttu-id="925f4-118">Comment</span><span class="sxs-lookup"><span data-stu-id="925f4-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="925f4-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="925f4-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="925f4-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="925f4-120">(0..63)</span></span>  | <span data-ttu-id="925f4-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="925f4-121">mdToken</span></span>     | <span data-ttu-id="925f4-122">*pVal* conterrà un Token completo.</span><span class="sxs-lookup"><span data-stu-id="925f4-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="925f4-123">La funzione converte automaticamente il Rid in un token completo.</span><span class="sxs-lookup"><span data-stu-id="925f4-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="925f4-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="925f4-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="925f4-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="925f4-125">(64..95)</span></span> | <span data-ttu-id="925f4-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="925f4-126">mdToken</span></span> | <span data-ttu-id="925f4-127">Al ritorno, *pVal* conterrà un Token completo.</span><span class="sxs-lookup"><span data-stu-id="925f4-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="925f4-128">La funzione decomprime automaticamente CodedToken in un token completo.</span><span class="sxs-lookup"><span data-stu-id="925f4-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="925f4-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="925f4-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="925f4-130">Int16</span><span class="sxs-lookup"><span data-stu-id="925f4-130">Int16</span></span>         | <span data-ttu-id="925f4-131">Firma automaticamente fino a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="925f4-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="925f4-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="925f4-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="925f4-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="925f4-133">UInt16</span></span>        | <span data-ttu-id="925f4-134">Firma automaticamente fino a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="925f4-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="925f4-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="925f4-135">`iLONG` (98)</span></span>             | <span data-ttu-id="925f4-136">Int32</span><span class="sxs-lookup"><span data-stu-id="925f4-136">Int32</span></span>         |                                        |
| <span data-ttu-id="925f4-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="925f4-137">`iULONG` (99)</span></span>            | <span data-ttu-id="925f4-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="925f4-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="925f4-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="925f4-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="925f4-140">Byte</span><span class="sxs-lookup"><span data-stu-id="925f4-140">Byte</span></span>          | <span data-ttu-id="925f4-141">Firma automaticamente fino a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="925f4-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="925f4-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="925f4-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="925f4-143">Indice heap stringhe</span><span class="sxs-lookup"><span data-stu-id="925f4-143">String heap index</span></span> | <span data-ttu-id="925f4-144">*pVal* è un indice nell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="925f4-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="925f4-145">Usare [IMetadataTables::GetString](imetadatatables-getstring-method.md) per ottenere il valore String della colonna effettiva.</span><span class="sxs-lookup"><span data-stu-id="925f4-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="925f4-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="925f4-146">`iGUID` (102)</span></span>            | <span data-ttu-id="925f4-147">Indice heap guid</span><span class="sxs-lookup"><span data-stu-id="925f4-147">Guid heap index</span></span> | <span data-ttu-id="925f4-148">*pVal* è un indice nell'heap Guid.</span><span class="sxs-lookup"><span data-stu-id="925f4-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="925f4-149">Usare [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) per ottenere il valore Guid della colonna effettiva.</span><span class="sxs-lookup"><span data-stu-id="925f4-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="925f4-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="925f4-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="925f4-151">Indice heap BLOB</span><span class="sxs-lookup"><span data-stu-id="925f4-151">Blob heap index</span></span> | <span data-ttu-id="925f4-152">*pVal* è un indice nell'heap Blob.pVal is an index into the Blob heap.</span><span class="sxs-lookup"><span data-stu-id="925f4-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="925f4-153">Usare [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) per ottenere il valore BLOB della colonna effettiva.</span><span class="sxs-lookup"><span data-stu-id="925f4-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="925f4-154">Requisiti</span><span class="sxs-lookup"><span data-stu-id="925f4-154">Requirements</span></span>  
 <span data-ttu-id="925f4-155">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="925f4-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="925f4-156">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="925f4-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="925f4-157">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="925f4-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="925f4-158">Versioni di **.NET Framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="925f4-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925f4-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="925f4-159">See also</span></span>

- [<span data-ttu-id="925f4-160">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="925f4-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="925f4-161">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="925f4-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
