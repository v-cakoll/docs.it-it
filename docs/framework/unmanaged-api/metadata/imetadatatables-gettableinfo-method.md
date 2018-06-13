---
title: Metodo IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea617668a72413f3387a35fe009b37fa15d03354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449608"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="0e8fd-102">Metodo IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="0e8fd-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="0e8fd-103">Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e8fd-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0e8fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e8fd-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="0e8fd-106">[in] Identificatore della tabella le cui proprietà da restituire.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="0e8fd-107">[out] Puntatore alla dimensione, in byte, di una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="0e8fd-108">[out] Puntatore al numero di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="0e8fd-109">[out] Puntatore al numero di colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="0e8fd-110">[out] Un puntatore all'indice della colonna chiave, oppure -1 se la tabella non ha una colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="0e8fd-111">[out] Un puntatore a un puntatore al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="0e8fd-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e8fd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e8fd-112">Requirements</span></span>  
 <span data-ttu-id="0e8fd-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e8fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e8fd-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0e8fd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e8fd-115">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0e8fd-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e8fd-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8fd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e8fd-117">See Also</span></span>  
 [<span data-ttu-id="0e8fd-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="0e8fd-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="0e8fd-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="0e8fd-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
