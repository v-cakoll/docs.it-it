---
title: Metodo AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1406c68f1f6abff4d140b131f5f630d0fd767e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787683"
---
# <a name="addfile-method"></a>Metodo AddFile
Aggiunge file all'assembly. Può essere usato anche per creare moduli non associati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID univoco dell'assembly da incrementare.  
  
 `pszFilename`  
 Nome completo del file da aggiungere.  
  
 `dwFlags`  
 Flag FileDef com+, ad `ffContainsNoMetaData` esempio `ffWriteable`e. `dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfaccia di [interfaccia IMetaDataEmit](../metadata/imetadataemit-interface.md) da usare per creare i metadati, se necessario.  
  
 `pFileToken`  
 Puntatore alla posizione in cui verrà archiviato l'ID univoco del file aggiunto.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
