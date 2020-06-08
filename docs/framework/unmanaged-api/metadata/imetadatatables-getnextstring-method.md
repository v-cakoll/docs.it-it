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
ms.openlocfilehash: 6f4764f016360a2ec0ab054b7a89ccb3f86aeb43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490224"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="476bf-102">Metodo IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="476bf-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="476bf-103">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="476bf-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="476bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="476bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="476bf-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="476bf-106">in Valore di indice da una colonna della tabella di stringhe.</span><span class="sxs-lookup"><span data-stu-id="476bf-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="476bf-107">out Puntatore all'indice della stringa successiva nella colonna.</span><span class="sxs-lookup"><span data-stu-id="476bf-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="476bf-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="476bf-108">Requirements</span></span>  
 <span data-ttu-id="476bf-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="476bf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="476bf-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="476bf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="476bf-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="476bf-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="476bf-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="476bf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476bf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="476bf-113">See also</span></span>

- [<span data-ttu-id="476bf-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="476bf-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="476bf-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="476bf-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
