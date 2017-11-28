---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a>GetScope Method1
Ottiene un ambito di importazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID univoco dell'assembly da importare.  
  
 `FileToken`  
 ID univoco del file da importare.  
  
 `dwScope`  
 Ambito in base zero da importare.  
  
 `ppImportScope`  
 Riceve [interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
