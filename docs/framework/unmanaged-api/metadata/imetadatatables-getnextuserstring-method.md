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
ms.openlocfilehash: 6522dbc8e49d612fc4c0d9597a9b5f12edb2cfe1
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937783"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="2f1a7-102">Metodo IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="2f1a7-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="2f1a7-103">Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="2f1a7-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f1a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f1a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f1a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f1a7-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="2f1a7-106">in Valore di indice della colonna stringa corrente.</span><span class="sxs-lookup"><span data-stu-id="2f1a7-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="2f1a7-107">out Puntatore all'indice di riga della stringa successiva nella colonna.</span><span class="sxs-lookup"><span data-stu-id="2f1a7-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f1a7-108">Note</span><span class="sxs-lookup"><span data-stu-id="2f1a7-108">Remarks</span></span>  
 <span data-ttu-id="2f1a7-109">Non è consigliabile usare questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="2f1a7-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="2f1a7-110">Per informazioni sulla tabella GUID, vedere la documentazione Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="2f1a7-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="2f1a7-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) e [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="2f1a7-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f1a7-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2f1a7-112">Requirements</span></span>  
 <span data-ttu-id="2f1a7-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f1a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f1a7-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2f1a7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f1a7-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2f1a7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f1a7-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f1a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1a7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f1a7-117">See also</span></span>

- [<span data-ttu-id="2f1a7-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="2f1a7-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2f1a7-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="2f1a7-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
