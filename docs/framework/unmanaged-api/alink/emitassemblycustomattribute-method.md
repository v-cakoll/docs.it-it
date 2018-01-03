---
title: Metodo EmitAssemblyCustomAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssemblyCustomAttribute
helpviewer_keywords: EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cc7709ef060642f12a8bc7d048e520427a5c674
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="emitassemblycustomattribute-method"></a>Metodo EmitAssemblyCustomAttribute
Chiamata eseguita per impostare gli attributi personalizzati a livello di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 File che definisce l'attributo. Può essere NULL se `AssemblyID` non indica un netmodule non associato.  
  
 `tkType`  
 Tipo dell'attributo personalizzato.  
  
 `pCustomValue`  
 Dati di valore personalizzato.  
  
 `cbCustomValue`  
 Lunghezza dei dati di valore personalizzato.  
  
 `bSecurity`  
 TRUE se l'attributo personalizzato è correlata alla firma dell'assembly.  
  
 `bAllowMulti`  
 TRUE se più attributi devono essere inviati.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
