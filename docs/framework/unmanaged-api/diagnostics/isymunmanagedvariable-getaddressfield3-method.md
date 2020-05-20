---
title: Metodo ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: ff888d3e2b86efeea3f4e3d33528f731d85886bf
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615267"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a>Metodo ISymUnmanagedVariable::GetAddressField3
Ottiene il terzo campo dell'indirizzo per questa variabile. Il suo significato dipende dal tipo di indirizzo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRetVal`  
 out Puntatore a un oggetto `ULONG32` che riceve il terzo campo dell'indirizzo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedVariable](isymunmanagedvariable-interface.md)
- [Metodo GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)
- [Metodo GetAddressField2](isymunmanagedvariable-getaddressfield2-method.md)
- [Metodo GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)
