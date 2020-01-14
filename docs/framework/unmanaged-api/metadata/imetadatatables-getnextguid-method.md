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
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937790"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="3e26e-102">Metodo IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="3e26e-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="3e26e-103">Ottiene l'indice del valore GUID successivo nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="3e26e-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e26e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e26e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e26e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e26e-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="3e26e-106">in Valore di indice da una colonna della tabella GUID.</span><span class="sxs-lookup"><span data-stu-id="3e26e-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="3e26e-107">out Puntatore all'indice del valore GUID successivo.</span><span class="sxs-lookup"><span data-stu-id="3e26e-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e26e-108">Note</span><span class="sxs-lookup"><span data-stu-id="3e26e-108">Remarks</span></span>  

  <span data-ttu-id="3e26e-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="3e26e-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="3e26e-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="3e26e-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="3e26e-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="3e26e-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e26e-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3e26e-112">Requirements</span></span>  
 <span data-ttu-id="3e26e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e26e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e26e-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e26e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e26e-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e26e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e26e-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e26e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e26e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e26e-117">See also</span></span>

- [<span data-ttu-id="3e26e-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="3e26e-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3e26e-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="3e26e-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
