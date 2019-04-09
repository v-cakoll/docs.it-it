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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119340"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="0ddcc-102">Metodo IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="0ddcc-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="0ddcc-103">Ottiene la stringa in corrispondenza dell'indice specificato della colonna di tabella presenti nell'ambito di riferimento corrente.</span><span class="sxs-lookup"><span data-stu-id="0ddcc-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddcc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ddcc-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ddcc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ddcc-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="0ddcc-106">[in] Indice in corrispondenza del quale iniziare a cercare il valore successivo.</span><span class="sxs-lookup"><span data-stu-id="0ddcc-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="0ddcc-107">[out] Puntatore a un puntatore al valore di stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="0ddcc-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddcc-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ddcc-108">Requirements</span></span>  
 <span data-ttu-id="0ddcc-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddcc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddcc-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ddcc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ddcc-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0ddcc-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0ddcc-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ddcc-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ddcc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ddcc-113">See also</span></span>

- [<span data-ttu-id="0ddcc-114">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="0ddcc-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0ddcc-115">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="0ddcc-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
