---
title: Metodo EmbedResource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98dbd32452184bf4f832bd66ffebb0fcf3d5bb0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="embedresource-method"></a>Metodo EmbedResource
Dichiara una risorsa incorporata. Questo metodo non incorpora la risorsa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 Token o assembly ID del file che contiene la risorsa.  
  
 `pszResourceName`  
 Nome della risorsa.  
  
 `dwOffset`  
 Offset della risorsa da RVA.  
  
 `dwFlags`  
 Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`. Questi flag possono essere passati a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
