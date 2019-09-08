---
title: Metodo AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777516"
---
# <a name="addfile2-method"></a>Metodo AddFile2
Aggiunge file all'assembly. Può essere usato anche per creare moduli non associati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly a cui viene aggiunto il file.  
  
 `pszFilename`  
 Nome del file da aggiungere.  
  
 `dwFlags`  
 Flag `FileDef` com+ `ffWriteable` `ffContainsNoMetaData` , ad esempio e. `dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfaccia per interfaccia dell' [Interfaccia IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .  
  
 `pFileToken`  
 Riceve l'ID per il file da aggiungere.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [Alink (API)](index.md)
