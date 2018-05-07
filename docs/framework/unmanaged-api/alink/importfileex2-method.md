---
title: Metodo ImportFileEx2
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be6332c76b3dae9c02e1a939286b70438ee14cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="importfileex2-method"></a>Metodo ImportFileEx2
Importa i moduli non associati e assembly. Questo metodo è simile [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ma funziona anche se il file da importare non esiste sul disco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome del file da importare.  
  
 `pszTargetName`  
 Nome facoltativo di file di destinazione.  
  
 `pAssemblyScopeIn`  
 Ambito di importazione opzionale [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.  
  
 `fSmartImport`  
 Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.  
  
 `dwOpenFlags`  
 Flag da passare a [OpenScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Riceve un ID univoco per l'assembly o file.  
  
 `ppAssemblyScope`  
 Riceve l'ambito di importazione assembly [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia. Può essere NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Riceve il numero di file e/o gli ambiti di importazione.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
