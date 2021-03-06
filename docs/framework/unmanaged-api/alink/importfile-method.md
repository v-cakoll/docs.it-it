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
ms.openlocfilehash: cda6d90865f8ad2b9d565f6a6378c35b03c65bf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446988"
---
# <a name="importfile-method"></a>Metodo ImportFile
Importa assembly e moduli non associati.  
  
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
 Nome del file di output facoltativo che può essere usato per rinominare il file mentre è collegato nell'assembly.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `pImportToken`  
 Puntatore al token in cui verrà archiviato un ID file univoco. Il file può essere un assembly o un file.  
  
 `ppAssemblyScope`  
 Riceve il puntatore all' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md). Può essere NULL se il file non è un assembly.  
  
 `pdwCountOfScopes`  
 Puntatore al conteggio dei file e/o degli ambiti che sono stati importati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
