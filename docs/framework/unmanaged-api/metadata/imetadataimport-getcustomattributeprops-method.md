---
title: Metodo IMetaDataImport::GetCustomAttributeProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 415b1dc67bd3ae3638edd61558cc9e13ebf03fd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>Metodo IMetaDataImport::GetCustomAttributeProps
Ottiene il valore dell'attributo personalizzato, dato il relativo token di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cv`  
 [in] Token di metadati che rappresenta l'attributo personalizzato da recuperare.  
  
 `ptkObj`  
 [out, facoltativo] Token di metadati che rappresenta l'oggetto che viene modificato dall'attributo personalizzato. Questo valore può essere un tipo qualsiasi di token di metadati, eccetto `mdCustomAttribute`.  
  
 `ptkType`  
 [out, facoltativo] Token di metadati `mdMethodDef` o `mdMemberRef` che rappresenta la classe <xref:System.Type> dell'attributo personalizzato restituito.  
  
 `ppBlob`  
 [out, facoltativo] Puntatore a una matrice di dati che è il valore dell'attributo personalizzato.  
  
 `pcbSize`  
 [out, facoltativo] Dimensione in byte dei dati restituiti in *`ppBlob`.  
  
## <a name="remarks"></a>Note  
 Un attributo personalizzato viene archiviato come matrice di dati, il formato riconosciuto dal modulo di gestione dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
