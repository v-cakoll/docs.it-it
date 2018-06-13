---
title: Metodo IMetaDataTables::GetNextGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca2c2b7c09f0b64fc8a2ffd6bd8455caa4c22215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448524"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="e7639-102">Metodo IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="e7639-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="e7639-103">Ottiene l'indice del successivo valore GUID nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="e7639-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7639-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7639-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7639-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7639-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="e7639-106">[in] Il valore di indice da una colonna di tabella GUID.</span><span class="sxs-lookup"><span data-stu-id="e7639-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="e7639-107">[out] Un puntatore all'indice del successivo valore GUID.</span><span class="sxs-lookup"><span data-stu-id="e7639-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7639-108">Note</span><span class="sxs-lookup"><span data-stu-id="e7639-108">Remarks</span></span>  
 <span data-ttu-id="e7639-109">Non è consigliabile l'utilizzo di questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="e7639-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="e7639-110">Per informazioni sulla tabella dei GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "partizione II: metadati definizione e la semantica".</span><span class="sxs-lookup"><span data-stu-id="e7639-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="e7639-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="e7639-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7639-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7639-112">Requirements</span></span>  
 <span data-ttu-id="e7639-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7639-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7639-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e7639-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7639-115">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e7639-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7639-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7639-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7639-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7639-117">See Also</span></span>  
 [<span data-ttu-id="e7639-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e7639-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e7639-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e7639-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
