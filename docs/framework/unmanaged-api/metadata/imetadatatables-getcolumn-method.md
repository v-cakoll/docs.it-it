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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442007"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="b2575-102">Metodo IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="b2575-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="b2575-103">Ottiene un puntatore al valore contenuto nella cella della colonna e della riga specificate nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="b2575-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2575-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2575-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2575-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2575-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="b2575-106">in Indice della tabella.</span><span class="sxs-lookup"><span data-stu-id="b2575-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="b2575-107">in Indice della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b2575-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="b2575-108">in Indice della riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b2575-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="b2575-109">out Puntatore al valore nella cella.</span><span class="sxs-lookup"><span data-stu-id="b2575-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="b2575-110">Note</span><span class="sxs-lookup"><span data-stu-id="b2575-110">Remarks</span></span>

<span data-ttu-id="b2575-111">L'interpretazione del valore restituito tramite `pVal` dipende dal tipo della colonna.</span><span class="sxs-lookup"><span data-stu-id="b2575-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="b2575-112">Il tipo di colonna può essere determinato chiamando [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="b2575-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="b2575-113">Il metodo **GetColumn** converte automaticamente le colonne di tipo **RID** o **CodedToken** in valori di `mdToken` a 32 bit completi.</span><span class="sxs-lookup"><span data-stu-id="b2575-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="b2575-114">Converte inoltre automaticamente i valori a 8 bit o a 16 bit in valori completi a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b2575-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="b2575-115">Per le colonne di tipo *heap* , il valore di *pval* restituito sarà un indice nell'heap corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b2575-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="b2575-116">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="b2575-116">Column type</span></span>              | <span data-ttu-id="b2575-117">pVal contiene</span><span class="sxs-lookup"><span data-stu-id="b2575-117">pVal contains</span></span> | <span data-ttu-id="b2575-118">Commento</span><span class="sxs-lookup"><span data-stu-id="b2575-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="b2575-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="b2575-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="b2575-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="b2575-120">(0..63)</span></span>  | <span data-ttu-id="b2575-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="b2575-121">mdToken</span></span>     | <span data-ttu-id="b2575-122">*pval* conterrà un token completo.</span><span class="sxs-lookup"><span data-stu-id="b2575-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="b2575-123">La funzione converte automaticamente il RID in un token completo.</span><span class="sxs-lookup"><span data-stu-id="b2575-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="b2575-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="b2575-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="b2575-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="b2575-125">(64..95)</span></span> | <span data-ttu-id="b2575-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="b2575-126">mdToken</span></span> | <span data-ttu-id="b2575-127">Al ritorno, *pval* conterrà un token completo.</span><span class="sxs-lookup"><span data-stu-id="b2575-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="b2575-128">La funzione decomprime automaticamente il CodedToken in un token completo.</span><span class="sxs-lookup"><span data-stu-id="b2575-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="b2575-129">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="b2575-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="b2575-130">Int16</span><span class="sxs-lookup"><span data-stu-id="b2575-130">Int16</span></span>         | <span data-ttu-id="b2575-131">Firma automaticamente estesa a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b2575-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="b2575-132">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="b2575-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="b2575-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="b2575-133">UInt16</span></span>        | <span data-ttu-id="b2575-134">Firma automaticamente estesa a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b2575-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="b2575-135">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="b2575-135">`iLONG` (98)</span></span>             | <span data-ttu-id="b2575-136">Int32</span><span class="sxs-lookup"><span data-stu-id="b2575-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="b2575-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="b2575-137">`iULONG` (99)</span></span>            | <span data-ttu-id="b2575-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="b2575-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="b2575-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="b2575-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="b2575-140">Byte</span><span class="sxs-lookup"><span data-stu-id="b2575-140">Byte</span></span>          | <span data-ttu-id="b2575-141">Firma automaticamente estesa a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b2575-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="b2575-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="b2575-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="b2575-143">Indice dell'heap delle stringhe</span><span class="sxs-lookup"><span data-stu-id="b2575-143">String heap index</span></span> | <span data-ttu-id="b2575-144">*pval* è un indice nell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="b2575-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="b2575-145">Usare [IMetadataTables:: GetString](imetadatatables-getstring-method.md) per ottenere il valore della stringa di colonna effettivo.</span><span class="sxs-lookup"><span data-stu-id="b2575-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="b2575-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="b2575-146">`iGUID` (102)</span></span>            | <span data-ttu-id="b2575-147">Indice heap GUID</span><span class="sxs-lookup"><span data-stu-id="b2575-147">Guid heap index</span></span> | <span data-ttu-id="b2575-148">*pval* è un indice nell'heap GUID.</span><span class="sxs-lookup"><span data-stu-id="b2575-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="b2575-149">Usare [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) per ottenere il valore effettivo del GUID della colonna.</span><span class="sxs-lookup"><span data-stu-id="b2575-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="b2575-150">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="b2575-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="b2575-151">Indice heap BLOB</span><span class="sxs-lookup"><span data-stu-id="b2575-151">Blob heap index</span></span> | <span data-ttu-id="b2575-152">*pval* è un indice nell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="b2575-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="b2575-153">Usare [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) per ottenere il valore effettivo del BLOB della colonna.</span><span class="sxs-lookup"><span data-stu-id="b2575-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="b2575-154">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2575-154">Requirements</span></span>  
 <span data-ttu-id="b2575-155">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2575-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2575-156">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b2575-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2575-157">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2575-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2575-158">**.NET Framework versioni** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2575-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2575-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2575-159">See also</span></span>

- [<span data-ttu-id="b2575-160">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b2575-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b2575-161">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b2575-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
