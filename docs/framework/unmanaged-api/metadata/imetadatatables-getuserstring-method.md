---
title: Metodo IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d7dee3da1967f8a958ea95ab4555f279c962f51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451795"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="56081-102">Metodo IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="56081-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="56081-103">Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="56081-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56081-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56081-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56081-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56081-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="56081-106">[in] Il valore di indice da cui verrà recuperata la stringa hardcoded.</span><span class="sxs-lookup"><span data-stu-id="56081-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="56081-107">[out] Puntatore alla dimensione del `ppData`.</span><span class="sxs-lookup"><span data-stu-id="56081-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="56081-108">[out] Un puntatore a un puntatore alla stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="56081-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56081-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56081-109">Requirements</span></span>  
 <span data-ttu-id="56081-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56081-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56081-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="56081-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56081-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="56081-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56081-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56081-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56081-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56081-114">See Also</span></span>  
 [<span data-ttu-id="56081-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="56081-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="56081-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="56081-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
