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
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437689"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="5a81f-102">Metodo IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="5a81f-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="5a81f-103">Ottiene l'attributo personalizzato, dato il nome e il proprietario.</span><span class="sxs-lookup"><span data-stu-id="5a81f-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a81f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a81f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a81f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a81f-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="5a81f-106">in Token di metadati che rappresenta l'oggetto proprietario dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5a81f-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="5a81f-107">in Nome dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5a81f-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="5a81f-108">out Puntatore a una matrice di dati che rappresenta il valore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5a81f-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="5a81f-109">out Dimensioni in byte dei dati restituiti in \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="5a81f-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a81f-110">Note</span><span class="sxs-lookup"><span data-stu-id="5a81f-110">Remarks</span></span>  
 <span data-ttu-id="5a81f-111">È consentito definire più attributi personalizzati per lo stesso proprietario; possono anche avere lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="5a81f-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="5a81f-112">Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza.</span><span class="sxs-lookup"><span data-stu-id="5a81f-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="5a81f-113">(`GetCustomAttributeByName` restituisce la prima istanza incontrata). Per trovare tutte le istanze di un attributo personalizzato, chiamare il metodo [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5a81f-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a81f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a81f-114">Requirements</span></span>  
 <span data-ttu-id="5a81f-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a81f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a81f-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a81f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a81f-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5a81f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a81f-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a81f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a81f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a81f-119">See also</span></span>

- [<span data-ttu-id="5a81f-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5a81f-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5a81f-121">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5a81f-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
