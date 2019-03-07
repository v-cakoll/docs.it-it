---
title: Metodo IMetaDataTables::GetColumn
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9c380d363830eb6b4c47110d50cdb4d08e4568d8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499810"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="5dc07-102">Metodo IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="5dc07-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="5dc07-103">Ottiene un puntatore al valore contenuto nella cella della colonna specificata e della riga nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="5dc07-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dc07-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dc07-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="5dc07-106">[in] L'indice della tabella.</span><span class="sxs-lookup"><span data-stu-id="5dc07-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="5dc07-107">[in] L'indice della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="5dc07-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="5dc07-108">[in] L'indice della riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="5dc07-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="5dc07-109">[out] Puntatore al valore della cella.</span><span class="sxs-lookup"><span data-stu-id="5dc07-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc07-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dc07-110">Requirements</span></span>  
 <span data-ttu-id="5dc07-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc07-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5dc07-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dc07-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5dc07-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc07-114">**Versioni di .NET framework** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc07-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc07-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dc07-115">See also</span></span>
- [<span data-ttu-id="5dc07-116">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5dc07-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5dc07-117">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5dc07-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
