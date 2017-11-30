---
title: Metodo IMetaDataTables::GetTableInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f4ccd9bbd1c7caa9bbeb548176d834dc8844213
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="cce30-102">Metodo IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="cce30-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="cce30-103">Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="cce30-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cce30-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cce30-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cce30-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="cce30-106">[in] Identificatore della tabella le cui proprietà da restituire.</span><span class="sxs-lookup"><span data-stu-id="cce30-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="cce30-107">[out] Puntatore alla dimensione, in byte, di una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="cce30-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="cce30-108">[out] Puntatore al numero di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="cce30-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="cce30-109">[out] Puntatore al numero di colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="cce30-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="cce30-110">[out] Un puntatore all'indice della colonna chiave, oppure -1 se la tabella non ha una colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="cce30-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="cce30-111">[out] Un puntatore a un puntatore al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="cce30-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cce30-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cce30-112">Requirements</span></span>  
 <span data-ttu-id="cce30-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cce30-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cce30-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cce30-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cce30-115">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cce30-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cce30-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cce30-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce30-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cce30-117">See Also</span></span>  
 [<span data-ttu-id="cce30-118">IMetaDataTables (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="cce30-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="cce30-119">IMetaDataTables2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="cce30-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
