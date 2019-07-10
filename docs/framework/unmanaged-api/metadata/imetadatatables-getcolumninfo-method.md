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
ms.openlocfilehash: c0755cb2a91d61725338562cb1fe249a9cfacc38
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781519"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="af94f-102">Metodo IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="af94f-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="af94f-103">Ottiene i dati relativi alla colonna specificata nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="af94f-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af94f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af94f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="af94f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af94f-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="af94f-106">[in] L'indice della tabella desiderata.</span><span class="sxs-lookup"><span data-stu-id="af94f-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="af94f-107">[in] L'indice della colonna desiderata.</span><span class="sxs-lookup"><span data-stu-id="af94f-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="af94f-108">[out] Un puntatore all'offset della colonna nella riga.</span><span class="sxs-lookup"><span data-stu-id="af94f-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="af94f-109">[out] Un puntatore alla dimensione, espressa in byte, della colonna.</span><span class="sxs-lookup"><span data-stu-id="af94f-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="af94f-110">[out] Un puntatore al tipo dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="af94f-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="af94f-111">[out] Un puntatore a un puntatore al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="af94f-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af94f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af94f-112">Requirements</span></span>  
 <span data-ttu-id="af94f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af94f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af94f-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="af94f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af94f-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="af94f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af94f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af94f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af94f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af94f-117">See also</span></span>

- [<span data-ttu-id="af94f-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="af94f-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="af94f-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="af94f-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
