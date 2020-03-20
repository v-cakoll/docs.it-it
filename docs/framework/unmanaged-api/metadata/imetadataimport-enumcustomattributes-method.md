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
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175525"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Metodo IMetaDataImport::EnumCustomAttributes
Enumera i token di definizione di attributo personalizzati associati al tipo o al membro specificato.  
  
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
 [in, out] Puntatore all'enumeratore restituito.  
  
 `tk`  
 [in] Token per l'ambito dell'enumerazione oppure zero per tutti gli attributi personalizzati.  
  
 `tkType`  
 [in] Token per il costruttore del tipo di attributi `null` da enumerare o per tutti i tipi.  
  
 `rCustomAttributes`  
 [fuori] Matrice di token di attributo personalizzati.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, opzionale] Numero effettivo di valori di `rCustomAttributes`token restituiti in .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes`restituito con successo.|  
|`S_FALSE`|Non sono presenti attributi personalizzati da enumerare. In tal `pcCustomAttributes` caso, è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
