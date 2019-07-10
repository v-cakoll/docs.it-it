---
title: Metodo IMetaDataImport::GetCustomAttributeByName
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bebf254110d9970ff3a99f948ff2e831ffb6b35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782442"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="aec82-102">Metodo IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="aec82-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="aec82-103">Ottiene l'attributo personalizzato, dato il relativo nome e il proprietario.</span><span class="sxs-lookup"><span data-stu-id="aec82-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aec82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aec82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aec82-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="aec82-106">[in] Un token di metadati che rappresenta l'oggetto che possiede l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aec82-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="aec82-107">[in] Il nome dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aec82-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="aec82-108">[out] Puntatore a una matrice di dati che corrisponde al valore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aec82-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="aec82-109">[out] La dimensione in byte dei dati restituiti \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="aec82-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec82-110">Note</span><span class="sxs-lookup"><span data-stu-id="aec82-110">Remarks</span></span>  
 <span data-ttu-id="aec82-111">È consentito definire più attributi personalizzati per lo stesso proprietario. possono anche presentare lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="aec82-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="aec82-112">Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza.</span><span class="sxs-lookup"><span data-stu-id="aec82-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="aec82-113">(`GetCustomAttributeByName` restituisce la prima istanza incontrata.) Per trovare tutte le istanze di un attributo personalizzato, chiamare il [EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="aec82-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec82-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aec82-114">Requirements</span></span>  
 <span data-ttu-id="aec82-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec82-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec82-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aec82-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aec82-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aec82-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aec82-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec82-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec82-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aec82-119">See also</span></span>

- [<span data-ttu-id="aec82-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="aec82-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="aec82-121">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="aec82-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
