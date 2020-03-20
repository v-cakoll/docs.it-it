---
title: Metodo IMetaDataTables::GetNextString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175252"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="d72dc-102">Metodo IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="d72dc-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="d72dc-103">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="d72dc-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d72dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d72dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d72dc-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="d72dc-106">[in] Valore di indice da una colonna di tabella di stringhe.</span><span class="sxs-lookup"><span data-stu-id="d72dc-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d72dc-107">[fuori] Puntatore all'indice della stringa successiva nella colonna.</span><span class="sxs-lookup"><span data-stu-id="d72dc-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72dc-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d72dc-108">Requirements</span></span>  
 <span data-ttu-id="d72dc-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d72dc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72dc-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d72dc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d72dc-111">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d72dc-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d72dc-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d72dc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72dc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d72dc-113">See also</span></span>

- [<span data-ttu-id="d72dc-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d72dc-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d72dc-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d72dc-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
