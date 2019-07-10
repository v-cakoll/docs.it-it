---
title: Metodo IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1be6079ed382b8ab27d0aec16bd725f5c5b9cb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778898"
---
# <a name="imetadataimportgetpinvokemap-method"></a>Metodo IMetaDataImport::GetPinvokeMap
Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 [in] Un token FieldDef o MethodDef per ottenere i metadati di mapping PInvoke per.  
  
 `pdwMappingFlags`  
 [out] Puntatore al flag utilizzati per il mapping. Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.  
  
 `szImportName`  
 [out] Nome della DLL di destinazione non gestita.  
  
 `cchImportName`  
 [in] La dimensione in caratteri "wide" di `szImportName`.  
  
 `pchImportName`  
 [out] Il numero di caratteri "wide", restituito nel `szImportName`.  
  
 `pmrImportDLL`  
 [out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
