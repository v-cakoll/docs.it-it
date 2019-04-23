---
title: Metodo ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c6279c790e9b28e5f3bac93d5d0fdd411dd8c0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127270"
---
# <a name="importfile2-method"></a>Metodo ImportFile2
Importa moduli non associati e assembly. Questo metodo è simile [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ma funziona anche se il file da importare non esiste sul disco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome del file da importare.  
  
 `pszTargetName`  
 Nome di file di output facoltativo che può essere utilizzato per rinominare il file perché è collegato nell'assembly.  
  
 `pAssemblyScopeIn`  
 Ambito facoltativo [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes, in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `pImportToken`  
 Riceve l'ID per il file o l'assembly.  
  
 `ppAssemblyScope`  
 Riceve la [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia. NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Riceve il conteggio dei file e/o ambiti importati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
