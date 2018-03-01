---
title: Metodo IMetaDataImport::GetCustomAttributeByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7d234a58d95203a26e8b1cab2cb936e6ee50c2fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="9a62e-102">Metodo IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="9a62e-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="9a62e-103">Ottiene l'attributo personalizzato, dato il nome e il proprietario.</span><span class="sxs-lookup"><span data-stu-id="9a62e-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a62e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a62e-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a62e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a62e-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="9a62e-106">[in] Un token di metadati che rappresenta l'oggetto che possiede l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9a62e-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="9a62e-107">[in] Il nome dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9a62e-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="9a62e-108">[out] Puntatore a una matrice di dati che rappresenta il valore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9a62e-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="9a62e-109">[out] Le dimensioni in byte dei dati restituiti \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="9a62e-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a62e-110">Note</span><span class="sxs-lookup"><span data-stu-id="9a62e-110">Remarks</span></span>  
 <span data-ttu-id="9a62e-111">È consentito definire più attributi personalizzati per lo stesso proprietario. è anche possibile che lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9a62e-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="9a62e-112">Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9a62e-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="9a62e-113">(`GetCustomAttributeByName` restituisce la prima istanza incontrata.) Per trovare tutte le istanze di un attributo personalizzato, chiamare il [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="9a62e-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a62e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a62e-114">Requirements</span></span>  
 <span data-ttu-id="9a62e-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a62e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a62e-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9a62e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a62e-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a62e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a62e-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a62e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a62e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a62e-119">See Also</span></span>  
 [<span data-ttu-id="9a62e-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9a62e-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9a62e-121">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9a62e-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
