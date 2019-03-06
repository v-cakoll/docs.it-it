---
title: Metodo IMetaDataTables::GetColumnInfo
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcab5adf30648f6b5a614a407478977bc37c7062
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480702"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="11cc9-102">Metodo IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="11cc9-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="11cc9-103">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="11cc9-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11cc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11cc9-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11cc9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11cc9-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="11cc9-106">[in] L'indice della tabella desiderata.</span><span class="sxs-lookup"><span data-stu-id="11cc9-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="11cc9-107">[in] L'indice della colonna desiderata.</span><span class="sxs-lookup"><span data-stu-id="11cc9-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="11cc9-108">[out] Un puntatore all'offset della colonna nella riga.</span><span class="sxs-lookup"><span data-stu-id="11cc9-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="11cc9-109">[out] Un puntatore alla dimensione, espressa in byte, della colonna.</span><span class="sxs-lookup"><span data-stu-id="11cc9-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="11cc9-110">[out] Un puntatore al tipo dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="11cc9-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="11cc9-111">[out] Un puntatore a un puntatore al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="11cc9-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11cc9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11cc9-112">Requirements</span></span>  
 <span data-ttu-id="11cc9-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11cc9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11cc9-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="11cc9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11cc9-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="11cc9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11cc9-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11cc9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cc9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11cc9-117">See also</span></span>
- [<span data-ttu-id="11cc9-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="11cc9-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="11cc9-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="11cc9-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
