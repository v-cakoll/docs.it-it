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
# <a name="imetadataimportgetcustomattributebyname-method"></a>Metodo IMetaDataImport::GetCustomAttributeByName
Ottiene l'attributo personalizzato, dato il relativo nome e il proprietario.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tkObj`  
 [in] Un token di metadati che rappresenta l'oggetto che possiede l'attributo personalizzato.  
  
 `szName`  
 [in] Il nome dell'attributo personalizzato.  
  
 `ppData`  
 [out] Puntatore a una matrice di dati che corrisponde al valore dell'attributo personalizzato.  
  
 `pcbData`  
 [out] La dimensione in byte dei dati restituiti *`ppData`.  
  
## <a name="remarks"></a>Note  
 È consentito definire più attributi personalizzati per lo stesso proprietario. possono anche presentare lo stesso nome. Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza. (`GetCustomAttributeByName` restituisce la prima istanza incontrata.) Per trovare tutte le istanze di un attributo personalizzato, chiamare il [EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
