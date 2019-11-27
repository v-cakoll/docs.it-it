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
ms.openlocfilehash: 48c38288e960ff2e1fe21f30b6eceae8eeaac2da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434850"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="62216-102">Metodo IMetaDataTables::GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="62216-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="62216-103">Ottiene l'indice per la tabella a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="62216-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62216-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62216-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62216-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62216-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="62216-106">in Token che fa riferimento alla tabella.</span><span class="sxs-lookup"><span data-stu-id="62216-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="62216-107">out Puntatore all'indice restituito per la tabella a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="62216-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62216-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="62216-108">Remarks</span></span>  
 <span data-ttu-id="62216-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="62216-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="62216-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="62216-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="62216-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="62216-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62216-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62216-112">Requirements</span></span>  
 <span data-ttu-id="62216-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62216-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62216-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62216-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62216-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62216-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62216-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62216-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62216-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62216-117">See also</span></span>

- [<span data-ttu-id="62216-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="62216-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="62216-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="62216-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
