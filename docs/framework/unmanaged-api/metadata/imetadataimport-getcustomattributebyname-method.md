---
title: Metodo IMetaDataImport::GetCustomAttributeByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b689c54b5e8d741d32bc941b4e78e6674f15e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="e11ad-102">Metodo IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="e11ad-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="e11ad-103">Ottiene l'attributo personalizzato, dato il nome e il proprietario.</span><span class="sxs-lookup"><span data-stu-id="e11ad-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e11ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e11ad-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e11ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e11ad-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="e11ad-106">[in] Un token di metadati che rappresenta l'oggetto che possiede l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e11ad-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="e11ad-107">[in] Il nome dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e11ad-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="e11ad-108">[out] Puntatore a una matrice di dati che rappresenta il valore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e11ad-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="e11ad-109">[out] Le dimensioni in byte dei dati restituiti *`ppData`.</span><span class="sxs-lookup"><span data-stu-id="e11ad-109">[out] The size in bytes of the data returned in *`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e11ad-110">Note</span><span class="sxs-lookup"><span data-stu-id="e11ad-110">Remarks</span></span>  
 <span data-ttu-id="e11ad-111">È consentito definire più attributi personalizzati per lo stesso proprietario. è anche possibile che lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="e11ad-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="e11ad-112">Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza.</span><span class="sxs-lookup"><span data-stu-id="e11ad-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="e11ad-113">(`GetCustomAttributeByName` restituisce la prima istanza incontrata.) Per trovare tutte le istanze di un attributo personalizzato, chiamare il [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="e11ad-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e11ad-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e11ad-114">Requirements</span></span>  
 <span data-ttu-id="e11ad-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e11ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e11ad-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e11ad-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e11ad-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e11ad-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e11ad-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e11ad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e11ad-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e11ad-119">See Also</span></span>  
 [<span data-ttu-id="e11ad-120">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e11ad-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e11ad-121">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e11ad-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
