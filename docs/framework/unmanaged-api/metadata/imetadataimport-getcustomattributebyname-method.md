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
ms.openlocfilehash: e6921a0f6420546ba1e866e37a7a7cb129a77c67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491459"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Metodo IMetaDataImport::GetCustomAttributeByName
Ottiene l'attributo personalizzato, dato il nome e il proprietario.  
  
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
 in Token di metadati che rappresenta l'oggetto proprietario dell'attributo personalizzato.  
  
 `szName`  
 in Nome dell'attributo personalizzato.  
  
 `ppData`  
 out Puntatore a una matrice di dati che rappresenta il valore dell'attributo personalizzato.  
  
 `pcbData`  
 out Dimensioni in byte dei dati restituiti in * `ppData` .  
  
## <a name="remarks"></a>Osservazioni  
 È consentito definire più attributi personalizzati per lo stesso proprietario; possono anche avere lo stesso nome. Tuttavia, `GetCustomAttributeByName` restituisce solo un'istanza. `GetCustomAttributeByName`restituisce la prima istanza di che rileva. Per trovare tutte le istanze di un attributo personalizzato, chiamare il metodo [IMetaDataImport:: EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
