---
title: Metodo IMetaDataImport::GetNameFromToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e77954d5730417a005c6c1ac07fa171bd0f1b13a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a>Metodo IMetaDataImport::GetNameFromToken
Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato. Questo metodo è obsoleto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tk`  
 [in] Che rappresenta l'oggetto per restituire il nome per il token.  
  
 `pszUtf8NamePtr`  
 [out] Un puntatore per il nome dell'oggetto nell'heap UTF-8.  
  
## <a name="remarks"></a>Note  
 `GetNameFromToken` è obsoleto. In alternativa, chiamare un metodo per ottenere le proprietà di quel determinato tipo di token richiesto, ad esempio `GetFieldProps` per un campo o `GetMethodProps` per un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:** 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
