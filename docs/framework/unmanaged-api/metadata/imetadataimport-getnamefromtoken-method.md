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
ms.openlocfilehash: 6d62739148280c7333cf7cdb6002b59a145496e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503562"
---
# <a name="imetadataimportgetnamefromtoken-method"></a>Metodo IMetaDataImport::GetNameFromToken
Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato. Questo metodo è obsoleto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 in Token che rappresenta l'oggetto per il quale restituire il nome.  
  
 `pszUtf8NamePtr`  
 out Puntatore al nome dell'oggetto UTF-8 nell'heap.  
  
## <a name="remarks"></a>Osservazioni  
 `GetNameFromToken` è obsoleto. In alternativa, chiamare un metodo per ottenere le proprietà del tipo specifico di token necessario, ad esempio `GetFieldProps` per un campo o `GetMethodProps` per un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
