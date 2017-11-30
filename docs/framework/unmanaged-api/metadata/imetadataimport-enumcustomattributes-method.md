---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 78a642ab3c9766ba32537e24814b3b0536df67c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
|`S_OK`|`EnumCustomAttributes`stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti attributi personalizzati da enumerare. In tal caso, `pcCustomAttributes` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
