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
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446512"
---
# <a name="emitassemblycustomattribute-method"></a>Metodo EmitAssemblyCustomAttribute
Chiamare per impostare gli attributi personalizzati a livello di assembly.  
  
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
 File che defilerà l'attributo. Può essere NULL se `AssemblyID` non indica un netmodule non associato.  
  
 `tkType`  
 Tipo dell'attributo personalizzato.  
  
 `pCustomValue`  
 Dati del valore personalizzato.  
  
 `cbCustomValue`  
 Lunghezza dei dati del valore personalizzato.  
  
 `bSecurity`  
 TRUE se l'attributo personalizzato è correlato alla firma dell'assembly.  
  
 `bAllowMulti`  
 TRUE se devono essere emessi più attributi.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
