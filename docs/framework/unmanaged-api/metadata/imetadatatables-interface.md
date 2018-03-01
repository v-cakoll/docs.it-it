---
title: Interfaccia IMetaDataTables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff70e99a963c929792a73cefd6e8feaefa8b252e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="195ed-102">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="195ed-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="195ed-103">Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="195ed-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="195ed-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="195ed-104">Methods</span></span>  
  
|<span data-ttu-id="195ed-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="195ed-105">Method</span></span>|<span data-ttu-id="195ed-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="195ed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="195ed-107">Metodo GetBlob</span><span class="sxs-lookup"><span data-stu-id="195ed-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="195ed-108">Ottiene un puntatore per l'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice della colonna specificata.</span><span class="sxs-lookup"><span data-stu-id="195ed-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="195ed-109">Metodo GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="195ed-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="195ed-110">Ottiene le dimensioni, in byte, dell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="195ed-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="195ed-111">Metodo GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="195ed-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="195ed-112">Ottiene un puntatore a una matrice di token associato all'indice di riga specificato.</span><span class="sxs-lookup"><span data-stu-id="195ed-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="195ed-113">Metodo GetColumn</span><span class="sxs-lookup"><span data-stu-id="195ed-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="195ed-114">Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificata, nella tabella in corrispondenza dell'indice di tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="195ed-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="195ed-115">Metodo GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="195ed-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="195ed-116">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="195ed-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="195ed-117">Metodo GetGuid</span><span class="sxs-lookup"><span data-stu-id="195ed-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="195ed-118">Ottiene un GUID della riga in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="195ed-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="195ed-119">Metodo GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="195ed-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="195ed-120">Ottiene le dimensioni, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="195ed-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="195ed-121">Metodo GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="195ed-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="195ed-122">Ottiene l'indice del successivo BLOB nella tabella.</span><span class="sxs-lookup"><span data-stu-id="195ed-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="195ed-123">Metodo GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="195ed-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="195ed-124">Ottiene l'indice del successivo valore GUID nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="195ed-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="195ed-125">Metodo GetNextString</span><span class="sxs-lookup"><span data-stu-id="195ed-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="195ed-126">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="195ed-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="195ed-127">Metodo GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="195ed-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="195ed-128">Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="195ed-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="195ed-129">Metodo GetNumTables</span><span class="sxs-lookup"><span data-stu-id="195ed-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="195ed-130">Ottiene il numero di tabelle nell'ambito dell'oggetto corrente `IMetaDataTables` istanza.</span><span class="sxs-lookup"><span data-stu-id="195ed-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="195ed-131">Metodo GetRow</span><span class="sxs-lookup"><span data-stu-id="195ed-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="195ed-132">Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="195ed-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="195ed-133">Metodo GetString</span><span class="sxs-lookup"><span data-stu-id="195ed-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="195ed-134">Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito di riferimento corrente.</span><span class="sxs-lookup"><span data-stu-id="195ed-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="195ed-135">Metodo GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="195ed-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="195ed-136">Ottiene le dimensioni, in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="195ed-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="195ed-137">Metodo GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="195ed-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="195ed-138">Ottiene l'indice per la tabella a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="195ed-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="195ed-139">Metodo GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="195ed-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="195ed-140">Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="195ed-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="195ed-141">Metodo GetUserString</span><span class="sxs-lookup"><span data-stu-id="195ed-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="195ed-142">Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="195ed-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="195ed-143">Metodo GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="195ed-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="195ed-144">Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="195ed-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="195ed-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="195ed-145">Requirements</span></span>  
 <span data-ttu-id="195ed-146">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195ed-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195ed-147">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="195ed-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="195ed-148">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="195ed-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="195ed-149">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195ed-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195ed-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="195ed-150">See Also</span></span>  
 [<span data-ttu-id="195ed-151">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="195ed-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="195ed-152">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="195ed-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
