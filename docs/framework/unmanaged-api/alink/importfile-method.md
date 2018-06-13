---
title: Metodo ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54b0a02af7f22e775e3f9567de79664c9805b4e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400650"
---
# <a name="importfile-method"></a>Metodo ImportFile
Importa i moduli non associati e assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome completo del file da importare.  
  
 `pszTargetName`  
 Nome di file di output facoltativo che può essere utilizzato per rinominare il file collegato nell'assembly.  
  
 `fSmartImport`  
 Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.  
  
 `pImportToken`  
 Puntatore al token in cui verrà archiviato un ID di file univoco. Il file può essere un assembly o un file.  
  
 `ppAssemblyScope`  
 Riceve il puntatore a [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Può essere NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Puntatore al numero di file e/o gli ambiti che sono stati importati.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
