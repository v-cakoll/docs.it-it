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
ms.openlocfilehash: 6f273cb03ad00957afb2bd78fe538a940fae236a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501235"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="b79a8-102">Metodo IMetaDataTables::GetGuid</span><span class="sxs-lookup"><span data-stu-id="b79a8-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="b79a8-103">Ottiene un GUID dalla riga in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="b79a8-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b79a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b79a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b79a8-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="b79a8-106">in Indice della riga da cui ottenere il GUID.</span><span class="sxs-lookup"><span data-stu-id="b79a8-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="b79a8-107">out Puntatore a un puntatore al GUID.</span><span class="sxs-lookup"><span data-stu-id="b79a8-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b79a8-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b79a8-108">Remarks</span></span>  

  <span data-ttu-id="b79a8-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="b79a8-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="b79a8-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="b79a8-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="b79a8-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="b79a8-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b79a8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b79a8-112">Requirements</span></span>  
 <span data-ttu-id="b79a8-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b79a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79a8-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b79a8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b79a8-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b79a8-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b79a8-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79a8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b79a8-117">See also</span></span>

- [<span data-ttu-id="b79a8-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b79a8-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b79a8-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b79a8-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
