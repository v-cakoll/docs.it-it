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
ms.openlocfilehash: a1c950e9a6e53e04cc0f2e52a140612562b32ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776975"
---
# <a name="importfileex2-method"></a>Metodo ImportFileEx2
Importa assembly e moduli non associati. Questo metodo è simile al [metodo ImportFile](importfile-method.md), ma funziona anche se il file importato non esiste sul disco.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome del file da importare.  
  
 `pszTargetName`  
 Nome facoltativo del file di destinazione.  
  
 `pAssemblyScopeIn`  
 Interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito di importazione facoltativa.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `dwOpenFlags`  
 Flag da passare al [Metodo OpenScope](../metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Riceve l'ID univoco per l'assembly o il file.  
  
 `ppAssemblyScope`  
 Riceve l'interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito di importazione assembly. Può essere NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Riceve il numero di file e/o ambiti importati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [Alink (API)](index.md)
