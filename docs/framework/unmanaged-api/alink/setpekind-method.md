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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787188"
---
# <a name="setpekind-method"></a>Metodo SetPEKind
Determina il tipo di eseguibile portatile, specifico del computer o indipendente dal computer.  
  
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
 Token del file per il quale deve essere impostato il tipo PE. Può essere null se `AssemblyID` non indica un netmodule non associato.  
  
 `dwPEKind`  
 Tipo di PE, come indicato dall' [enumerazione CorPEKind](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 L'architettura del computer di destinazione, come indicato nell'intestazione NT.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [Alink (API)](index.md)
