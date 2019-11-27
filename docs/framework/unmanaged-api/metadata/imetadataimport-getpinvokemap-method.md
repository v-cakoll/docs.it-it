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
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437106"
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
 in Token FieldDef o MethodDef per il quale ottenere i metadati del mapping PInvoke.  
  
 `pdwMappingFlags`  
 out Puntatore ai flag utilizzati per il mapping. Questo valore è una maschera di maschera dall'enumerazione [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) .  
  
 `szImportName`  
 out Nome della DLL di destinazione non gestita.  
  
 `cchImportName`  
 in Dimensioni in caratteri wide di `szImportName`.  
  
 `pchImportName`  
 out Numero di caratteri wide restituiti in `szImportName`.  
  
 `pmrImportDLL`  
 out Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
