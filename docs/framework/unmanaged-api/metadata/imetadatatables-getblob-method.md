---
title: Metodo IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 743fb1c77e2dd74487a7498be25ea23b4919032a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447299"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="e39b3-102">Metodo IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="e39b3-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="e39b3-103">Ottiene un puntatore per l'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice della colonna specificata.</span><span class="sxs-lookup"><span data-stu-id="e39b3-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e39b3-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e39b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e39b3-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="e39b3-106">[in] L'indirizzo di memoria da cui ottenere `ppData`.</span><span class="sxs-lookup"><span data-stu-id="e39b3-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="e39b3-107">[out] Un puntatore alla dimensione, in byte, di `ppData`.</span><span class="sxs-lookup"><span data-stu-id="e39b3-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="e39b3-108">[out] Recuperata un puntatore a un puntatore ai dati binari.</span><span class="sxs-lookup"><span data-stu-id="e39b3-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e39b3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e39b3-109">Requirements</span></span>  
 <span data-ttu-id="e39b3-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e39b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e39b3-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e39b3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e39b3-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e39b3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e39b3-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e39b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39b3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e39b3-114">See Also</span></span>  
 [<span data-ttu-id="e39b3-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e39b3-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e39b3-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e39b3-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
