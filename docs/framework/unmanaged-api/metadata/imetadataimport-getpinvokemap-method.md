---
title: Metodo IMetaDataImport::GetPinvokeMap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: adb6a9a5f53dcfd8ada5b3aa9d75daac18d50283
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a>Metodo IMetaDataImport::GetPinvokeMap
Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tk`  
 [in] Token FieldDef o MethodDef per ottenere i metadati di mapping per PInvoke.  
  
 `pdwMappingFlags`  
 [out] Puntatore a flag utilizzati per il mapping. Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.  
  
 `szImportName`  
 [out] Il nome della DLL di destinazione non gestita.  
  
 `cchImportName`  
 [in] La dimensione in caratteri "wide" di `szImportName`.  
  
 `pchImportName`  
 [out] Il numero di caratteri "wide" restituiti in `szImportName`.  
  
 `pmrImportDLL`  
 [out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
