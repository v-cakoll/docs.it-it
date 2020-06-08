---
title: Interfaccia IMetaDataTables
ms.date: 03/30/2017
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
ms.openlocfilehash: 2105033e684ec172e24adfb14bcab7668b388af3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501121"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="06b99-102">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="06b99-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="06b99-103">Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="06b99-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06b99-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="06b99-104">Methods</span></span>  
  
|<span data-ttu-id="06b99-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="06b99-105">Method</span></span>|<span data-ttu-id="06b99-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06b99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06b99-107">Metodo GetBlob</span><span class="sxs-lookup"><span data-stu-id="06b99-107">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="06b99-108">Ottiene un puntatore all'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice di colonna specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="06b99-109">Metodo GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="06b99-109">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="06b99-110">Ottiene la dimensione, in byte, dell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="06b99-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="06b99-111">Metodo GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="06b99-111">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="06b99-112">Ottiene un puntatore a una matrice di token associati all'indice di riga specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="06b99-113">Metodo GetColumn</span><span class="sxs-lookup"><span data-stu-id="06b99-113">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="06b99-114">Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificato, nella tabella in corrispondenza dell'indice di tabella specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="06b99-115">Metodo GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="06b99-115">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="06b99-116">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="06b99-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="06b99-117">Metodo GetGuid</span><span class="sxs-lookup"><span data-stu-id="06b99-117">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="06b99-118">Ottiene un GUID dalla riga in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="06b99-119">Metodo GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="06b99-119">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="06b99-120">Ottiene la dimensione, in byte, dell'heap GUID.</span><span class="sxs-lookup"><span data-stu-id="06b99-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="06b99-121">Metodo GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="06b99-121">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="06b99-122">Ottiene l'indice del BLOB successivo nella tabella.</span><span class="sxs-lookup"><span data-stu-id="06b99-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="06b99-123">Metodo GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="06b99-123">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="06b99-124">Ottiene l'indice del valore GUID successivo nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="06b99-125">Metodo GetNextString</span><span class="sxs-lookup"><span data-stu-id="06b99-125">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="06b99-126">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="06b99-127">Metodo GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="06b99-127">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="06b99-128">Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="06b99-129">Metodo GetNumTables</span><span class="sxs-lookup"><span data-stu-id="06b99-129">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="06b99-130">Ottiene il numero di tabelle nell'ambito dell' `IMetaDataTables` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="06b99-131">Metodo GetRow</span><span class="sxs-lookup"><span data-stu-id="06b99-131">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="06b99-132">Ottiene la riga in corrispondenza dell'indice di riga specificato, nella tabella in corrispondenza dell'indice di tabella specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="06b99-133">Metodo GetString</span><span class="sxs-lookup"><span data-stu-id="06b99-133">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="06b99-134">Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito del riferimento corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="06b99-135">Metodo GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="06b99-135">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="06b99-136">Ottiene la dimensione, in byte, dell'heap delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="06b99-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="06b99-137">Metodo GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="06b99-137">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="06b99-138">Ottiene l'indice per la tabella a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="06b99-139">Metodo GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="06b99-139">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="06b99-140">Ottiene il nome, le dimensioni della riga, il numero di righe, il numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificato.</span><span class="sxs-lookup"><span data-stu-id="06b99-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="06b99-141">Metodo GetUserString</span><span class="sxs-lookup"><span data-stu-id="06b99-141">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="06b99-142">Ottiene la stringa hardcoded in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="06b99-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="06b99-143">Metodo GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="06b99-143">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="06b99-144">Ottiene la dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="06b99-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06b99-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06b99-145">Requirements</span></span>  
 <span data-ttu-id="06b99-146">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06b99-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b99-147">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06b99-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06b99-148">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06b99-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06b99-149">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b99-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b99-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06b99-150">See also</span></span>

- [<span data-ttu-id="06b99-151">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="06b99-151">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="06b99-152">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="06b99-152">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
