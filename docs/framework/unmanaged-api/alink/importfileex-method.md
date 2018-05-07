---
title: Metodo ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fe73bef50a32c3ff03f2a2754f665cc95018a4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="importfileex-method"></a>Metodo ImportFileEx
Importazioni indicato assembly o un modulo non associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome completo del file da cui importare.  
  
 `pszTargetName`  
 Nome facoltativo di file di destinazione.  
  
 `fSmartImport`  
 Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.  
  
 `dwOpenFlags`  
 Flag da passare a [OpenScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Riceve l'ID del file da importare.  
  
 `ppAssemblyScope`  
 Riceve l'ambito di importazione assembly [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia. È impostato su NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Riceve il numero di file importati e/o gli ambiti.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
