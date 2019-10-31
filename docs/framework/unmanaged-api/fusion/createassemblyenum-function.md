---
title: Funzione CreateAssemblyEnum
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: 0e54027806cef07fad4740c3bf5226fd26c72570
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108772"
---
# <a name="createassemblyenum-function"></a>Funzione CreateAssemblyEnum
Ottiene un puntatore a un'istanza di [IAssemblyEnum](iassemblyenum-interface.md) in grado di enumerare gli oggetti nell'assembly con il [IAssemblyName](iassemblyname-interface.md)specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pEnum`  
 out Puntatore a una posizione di memoria che contiene il puntatore `IAssemblyEnum` richiesto.  
  
 `pUnkReserved`  
 in Riservato per l'estendibilità futura. `pUnkReserved` deve essere un riferimento null.  
  
 `pName`  
 in `IAssemblyName` dell'assembly richiesto. Questo nome viene usato per filtrare l'enumerazione. Può essere null per enumerare tutti gli assembly nella Global Assembly Cache.  
  
 `dwFlags`  
 in Flag per la modifica del comportamento dell'enumeratore. Questo parametro contiene esattamente un bit dell'enumerazione [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved` deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il parametro `dwFlags` contiene esattamente un bit dell'enumerazione `ASM_CACHE_FLAGS`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyEnum](iassemblyenum-interface.md)
- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
