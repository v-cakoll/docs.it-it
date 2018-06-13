---
title: Metodo IMetaDataTables::GetNextBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caf7faeea4bcec9b73f3c43f0923d308baebf6d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447620"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="3e31f-102">Metodo IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="3e31f-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="3e31f-103">Ottiene l'indice del successivo oggetto binario di grandi dimensioni (BLOB) nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3e31f-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e31f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e31f-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e31f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e31f-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="3e31f-106">[in] L'indice, come restituito da una colonna di BLOB.</span><span class="sxs-lookup"><span data-stu-id="3e31f-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="3e31f-107">[out] Un puntatore all'indice del successivo BLOB.</span><span class="sxs-lookup"><span data-stu-id="3e31f-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e31f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e31f-108">Requirements</span></span>  
 <span data-ttu-id="3e31f-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e31f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e31f-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e31f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e31f-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3e31f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e31f-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e31f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e31f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e31f-113">See Also</span></span>  
 [<span data-ttu-id="3e31f-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="3e31f-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="3e31f-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="3e31f-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
