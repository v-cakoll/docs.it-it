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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eea43e5eaa037a3b70f482b0602d8d8d3d594f75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449849"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="265c5-102">Metodo IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="265c5-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="265c5-103">Ottiene l'indice della stringa successiva nella colonna della tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="265c5-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="265c5-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="265c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="265c5-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="265c5-106">[in] Il valore di indice da una colonna di tabella della stringa.</span><span class="sxs-lookup"><span data-stu-id="265c5-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="265c5-107">[out] Un puntatore all'indice della stringa nella colonna successiva.</span><span class="sxs-lookup"><span data-stu-id="265c5-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265c5-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="265c5-108">Requirements</span></span>  
 <span data-ttu-id="265c5-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="265c5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265c5-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="265c5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="265c5-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="265c5-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="265c5-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265c5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265c5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="265c5-113">See Also</span></span>  
 [<span data-ttu-id="265c5-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="265c5-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="265c5-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="265c5-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
