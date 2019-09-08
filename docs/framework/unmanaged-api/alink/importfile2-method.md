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
ms.openlocfilehash: a03fc24e5ef932d13c0d195f53c703cdd3ff45ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776934"
---
# <a name="importfile2-method"></a>Metodo ImportFile2
Importa assembly e moduli non associati. Questo metodo è simile al [metodo ImportFile](importfile-method.md), ma funziona anche se il file importato non esiste sul disco.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 Nome del file di output facoltativo che può essere usato per rinominare il file mentre è collegato nell'assembly.  
  
 `pAssemblyScopeIn`  
 Interfaccia facoltativa dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `pImportToken`  
 Riceve l'ID per il file o l'assembly.  
  
 `ppAssemblyScope`  
 Riceve l'interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) . NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Riceve l'oggetto trovato dei file e/o degli ambiti importati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
