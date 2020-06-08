---
title: Metodo IMetaDataTables::GetNextUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: 3490eec7c3b59ab8f4158498e2731773b6491b42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490185"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="db4c2-102">Metodo IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="db4c2-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="db4c2-103">Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="db4c2-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db4c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db4c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db4c2-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="db4c2-106">in Valore di indice della colonna stringa corrente.</span><span class="sxs-lookup"><span data-stu-id="db4c2-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="db4c2-107">out Puntatore all'indice di riga della stringa successiva nella colonna.</span><span class="sxs-lookup"><span data-stu-id="db4c2-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db4c2-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db4c2-108">Remarks</span></span>  
 <span data-ttu-id="db4c2-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="db4c2-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="db4c2-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="db4c2-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="db4c2-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="db4c2-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db4c2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db4c2-112">Requirements</span></span>  
 <span data-ttu-id="db4c2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db4c2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db4c2-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="db4c2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db4c2-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="db4c2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db4c2-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db4c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4c2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db4c2-117">See also</span></span>

- [<span data-ttu-id="db4c2-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="db4c2-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="db4c2-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="db4c2-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
