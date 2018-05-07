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
ms.openlocfilehash: b549c6eacad63b165d26c203817f1a2adac57bca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumcustomattributes-method"></a>Metodo IMetaDataImport::EnumCustomAttributes
Enumera i token di definizione di attributo personalizzato associati al tipo specificato o un membro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore restituito.  
  
 `tk`  
 [in] Un token per l'ambito di enumerazione, oppure zero per tutti gli attributi personalizzati.  
  
 `tkType`  
 [in] Un token per il costruttore del tipo di attributi da enumerare o `null` per tutti i tipi.  
  
 `rCustomAttributes`  
 [out] Matrice di token di attributi personalizzati.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, facoltativo] Il numero effettivo di valori token restituiti `rCustomAttributes`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti attributi personalizzati da enumerare. In tal caso, `pcCustomAttributes` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
