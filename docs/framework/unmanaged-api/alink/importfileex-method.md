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
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777122"
---
# <a name="importfileex-method"></a>Metodo ImportFileEx
Importa l'assembly indicato o il modulo non associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome completo del file da cui eseguire l'importazione.  
  
 `pszTargetName`  
 Nome facoltativo del file di destinazione.  
  
 `fSmartImport`  
 Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.  
  
 `dwOpenFlags`  
 Flag da passare al [Metodo OpenScope](../metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Riceve l'ID del file importato.  
  
 `ppAssemblyScope`  
 Riceve l'interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito di importazione assembly. È impostato su NULL se il file non è un assembly.  
  
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
