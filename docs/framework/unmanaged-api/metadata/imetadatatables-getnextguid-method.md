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
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042367"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="f9b02-102">Metodo IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="f9b02-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="f9b02-103">Ottiene l'indice del valore del GUID successivo nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="f9b02-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9b02-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9b02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9b02-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="f9b02-106">[in] Il valore di indice da una colonna di tabella GUID.</span><span class="sxs-lookup"><span data-stu-id="f9b02-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="f9b02-107">[out] Un puntatore all'indice del successivo valore GUID.</span><span class="sxs-lookup"><span data-stu-id="f9b02-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9b02-108">Note</span><span class="sxs-lookup"><span data-stu-id="f9b02-108">Remarks</span></span>  
 <span data-ttu-id="f9b02-109">Non è consigliabile l'uso di questo metodo, perché non restituire risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="f9b02-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f9b02-110">Per informazioni sulla tabella di GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="f9b02-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f9b02-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="f9b02-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9b02-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9b02-112">Requirements</span></span>  
 <span data-ttu-id="f9b02-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9b02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9b02-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f9b02-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9b02-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f9b02-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9b02-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9b02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b02-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9b02-117">See also</span></span>

- [<span data-ttu-id="f9b02-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f9b02-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f9b02-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f9b02-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
