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
ms.openlocfilehash: 22f9ceab2f01ac12762710f313c56f3f0ee4e6be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781541"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="00305-102">Metodo IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="00305-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="00305-103">Ottiene un puntatore al valore contenuto nella cella della colonna specificata e della riga nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="00305-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00305-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00305-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00305-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00305-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="00305-106">[in] L'indice della tabella.</span><span class="sxs-lookup"><span data-stu-id="00305-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="00305-107">[in] L'indice della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="00305-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="00305-108">[in] L'indice della riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="00305-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="00305-109">[out] Puntatore al valore della cella.</span><span class="sxs-lookup"><span data-stu-id="00305-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00305-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00305-110">Requirements</span></span>  
 <span data-ttu-id="00305-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00305-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00305-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="00305-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00305-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="00305-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00305-114">**Versioni di .NET framework** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00305-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00305-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00305-115">See also</span></span>

- [<span data-ttu-id="00305-116">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="00305-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="00305-117">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="00305-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
