---
title: Metodo IMetaDataTables::GetTableIndex
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: d3e056bc93c2faf2b1509536b8d8d4df6886dd20
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937374"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="ea1b9-102">Metodo IMetaDataTables::GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="ea1b9-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="ea1b9-103">Ottiene l'indice per la tabella a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="ea1b9-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea1b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea1b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea1b9-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="ea1b9-106">in Token che fa riferimento alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ea1b9-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="ea1b9-107">out Puntatore all'indice restituito per la tabella a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ea1b9-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea1b9-108">Note</span><span class="sxs-lookup"><span data-stu-id="ea1b9-108">Remarks</span></span>  
 <span data-ttu-id="ea1b9-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="ea1b9-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ea1b9-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="ea1b9-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ea1b9-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ea1b9-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1b9-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ea1b9-112">Requirements</span></span>  
 <span data-ttu-id="ea1b9-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1b9-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ea1b9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea1b9-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ea1b9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea1b9-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1b9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea1b9-117">See also</span></span>

- [<span data-ttu-id="ea1b9-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ea1b9-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ea1b9-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ea1b9-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
