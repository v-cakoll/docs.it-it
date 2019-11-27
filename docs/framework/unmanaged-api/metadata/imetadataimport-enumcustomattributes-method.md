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
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440247"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Metodo IMetaDataImport::EnumCustomAttributes
Enumera i token di definizione degli attributi personalizzati associati al tipo o al membro specificato.  
  
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
 in Token per l'ambito dell'enumerazione o zero per tutti gli attributi personalizzati.  
  
 `tkType`  
 in Token per il costruttore del tipo degli attributi da enumerare o `null` per tutti i tipi.  
  
 `rCustomAttributes`  
 out Matrice di token di attributi personalizzati.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, facoltativo] Numero effettivo di valori di token restituiti in `rCustomAttributes`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun attributo personalizzato da enumerare. In tal caso, `pcCustomAttributes` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
