---
title: Metodo IMetaDataTables::GetGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175278"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="19c78-102">Metodo IMetaDataTables::GetGuid</span><span class="sxs-lookup"><span data-stu-id="19c78-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="19c78-103">Ottiene un GUID dalla riga in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="19c78-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c78-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19c78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19c78-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19c78-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="19c78-106">[in] Indice della riga da cui ottenere il GUID.</span><span class="sxs-lookup"><span data-stu-id="19c78-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="19c78-107">[fuori] Puntatore a un puntatore al GUID.</span><span class="sxs-lookup"><span data-stu-id="19c78-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19c78-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="19c78-108">Remarks</span></span>  

  <span data-ttu-id="19c78-109">Non è consigliabile utilizzare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="19c78-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="19c78-110">Per informazioni sulla tabella GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="19c78-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="19c78-111">La documentazione è disponibile online; vedere [ECMA c'è e Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e Standard [ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="19c78-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c78-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19c78-112">Requirements</span></span>  
 <span data-ttu-id="19c78-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c78-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19c78-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19c78-115">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19c78-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19c78-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c78-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c78-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c78-117">See also</span></span>

- [<span data-ttu-id="19c78-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="19c78-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="19c78-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="19c78-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
