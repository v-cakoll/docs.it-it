---
title: Metodo EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfcc2db3f1f0d8646f903fedb1eb06b39928d00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742129"
---
# <a name="emitassemblycustomattribute-method"></a>Metodo EmitAssemblyCustomAttribute
Chiamata per impostare gli attributi personalizzati a livello di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 File che definisce l'attributo. Può essere NULL se `AssemblyID` non indica un netmodule non associato.  
  
 `tkType`  
 Tipo dell'attributo personalizzato.  
  
 `pCustomValue`  
 Dati valore personalizzato.  
  
 `cbCustomValue`  
 Lunghezza dei dati di valore personalizzato.  
  
 `bSecurity`  
 TRUE se l'attributo personalizzato è correlata alla firma dell'assembly.  
  
 `bAllowMulti`  
 TRUE se devono essere emesse più attributi.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
