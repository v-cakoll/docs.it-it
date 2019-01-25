---
title: Metodo1 AddImport
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
ms.openlocfilehash: d2daed0450e04137621788e830bbedb467bd57c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706339"
---
# <a name="addimport-method1"></a>Metodo1 AddImport
Aggiunge le importazioni dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID univoco dell'assembly da ampliare.  
  
 `ImportToken`  
 ID univoco, recuperato dal [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del file da importare.  
  
 `dwFlags`  
 Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`. `dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Puntatore al token che riceve l'ID per il file risultante.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
