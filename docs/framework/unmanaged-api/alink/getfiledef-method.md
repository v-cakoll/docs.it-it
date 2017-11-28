---
title: Metodo GetFileDef
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetFileDef
api_location: alink.dll
api_type: COM
f1_keywords: GetFileDef
helpviewer_keywords: GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a31dee6bb1af4f555211822a3b7ec108353214a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getfiledef-method"></a>Metodo GetFileDef
Recupera il token FileDef effettivamente utilizzato nei metadati (a differenza dei token assegnato da ALink).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `TargetFile`  
 Token del file aggiunto così come viene recuperato dal metodo AddFile o dal metodo AddImport.  
  
 `pScope`  
 Riceve il token FileDef.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
