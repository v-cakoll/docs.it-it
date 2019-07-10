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
ms.openlocfilehash: d76e9b4e18b46d0b546d6c66fa572c35cb9fcefe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741775"
---
# <a name="importfile-method"></a>Metodo ImportFile
Importa moduli non associati e assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome completo del file da importare.  
  
 `pszTargetName`  
 Nome di file di output facoltativo che può essere utilizzato per rinominare il file perché è collegato nell'assembly.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes, in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `pImportToken`  
 Puntatore al token in cui verrà archiviato un ID di file univoco. Il file può essere un assembly o un file.  
  
 `ppAssemblyScope`  
 Riceve il puntatore alla [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Può essere NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Puntatore al numero di file e/o gli ambiti che sono stati importati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
