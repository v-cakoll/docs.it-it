---
title: Metodo SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179381"
---
# <a name="setpekind-method"></a>Metodo SetPEKind
Determina il tipo di eseguibile portabile, specifico del computer o indipendente dal computer.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 Token del file per il quale deve essere impostato il tipo PE. Può essere `AssemblyID` NULL se non indica un netmodule non associato.  
  
 `dwPEKind`  
 Tipo di PE, come indicato [dall'enumerazione CorPEKind](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Architettura del computer di destinazione, come indicato nell'intestazione NT.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [API Alink](index.md)
