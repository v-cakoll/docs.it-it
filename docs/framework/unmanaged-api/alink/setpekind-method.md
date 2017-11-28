---
title: Metodo SetPEKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a>Metodo SetPEKind
Determina il tipo di file eseguibile portabile, specifiche del computer o indipendente dal computer.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 Token del file per cui è necessario impostare il tipo PE. Può essere NULL se `AssemblyID` non indica un netmodule non associato.  
  
 `dwPEKind`  
 Il tipo di PE, come indicato dal [Enumerazione CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Architettura del computer di destinazione, come indicato nell'intestazione NT.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche  
 [GetPEKind (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
