---
title: Metodo IMetaDataImport::GetNameFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36218fa44f1cb49d8d0193d7c72e6feb2d121050
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718845"
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
 [out] Puntatore al nome dell'oggetto UTF-8 nell'heap.  
  
## <a name="remarks"></a>Note  
 `GetNameFromToken` è obsoleto. In alternativa, chiamare un metodo per ottenere le proprietà del tipo di token richiesto, come determinato `GetFieldProps` per un campo o `GetMethodProps` per un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** 1.0  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
