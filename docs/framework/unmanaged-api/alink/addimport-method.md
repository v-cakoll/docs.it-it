---
title: Metodo AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787661"
---
# <a name="addimport-method"></a>Metodo AddImport
Aggiunge le importazioni all'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID univoco dell'assembly da incrementare.  
  
 `ImportToken`  
 ID univoco, recuperato dal [metodo ImportFile](importfile-method.md), del file da importare.  
  
 `dwFlags`  
 Flag FileDef com+, ad `ffContainsNoMetaData` esempio `ffWriteable`e. `dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Puntatore al token che riceve l'ID per il file risultante.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
