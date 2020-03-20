---
title: Metodo IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 216a1f7bd2ff5a596fa7abf7874b5e603d5a9f7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175239"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="32c6d-102">Metodo IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="32c6d-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="32c6d-103">Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito di riferimento corrente.</span><span class="sxs-lookup"><span data-stu-id="32c6d-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32c6d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32c6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32c6d-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="32c6d-106">[in] Indice in corrispondenza del quale iniziare la ricerca del valore successivo.</span><span class="sxs-lookup"><span data-stu-id="32c6d-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="32c6d-107">[fuori] Puntatore a un puntatore al valore stringa restituito.</span><span class="sxs-lookup"><span data-stu-id="32c6d-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c6d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32c6d-108">Requirements</span></span>  
 <span data-ttu-id="32c6d-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32c6d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c6d-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32c6d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32c6d-111">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32c6d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32c6d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c6d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c6d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32c6d-113">See also</span></span>

- [<span data-ttu-id="32c6d-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="32c6d-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="32c6d-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="32c6d-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
