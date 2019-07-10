---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c38b7f060c34f7408195484dec2c49305db422fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781315"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Metodo IMetaDataImport::EnumCustomAttributes
Enumera i token di definizione di attributo personalizzato associati con il tipo specificato o il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore restituito.  
  
 `tk`  
 [in] Un token per l'ambito di enumerazione o zero per tutti gli attributi personalizzati.  
  
 `tkType`  
 [in] Un token per il costruttore del tipo degli attributi da enumerare, o `null` per tutti i tipi.  
  
 `rCustomAttributes`  
 [out] Matrice dei token di attributo personalizzato.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, optional] Il numero effettivo di valori del token restituito nel `rCustomAttributes`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti attributi personalizzati da enumerare. In tal caso, `pcCustomAttributes` è uguale a zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
