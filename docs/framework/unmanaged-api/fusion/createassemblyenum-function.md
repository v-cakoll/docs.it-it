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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795381"
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
 out Puntatore a una posizione di memoria che contiene il `IAssemblyEnum` puntatore richiesto.  
  
 `pUnkReserved`  
 in Riservato per l'estendibilità futura. `pUnkReserved`deve essere un riferimento null.  
  
 `pName`  
 in Oggetto `IAssemblyName` dell'assembly richiesto. Questo nome viene usato per filtrare l'enumerazione. Può essere null per enumerare tutti gli assembly nella Global Assembly Cache.  
  
 `dwFlags`  
 in Flag per la modifica del comportamento dell'enumeratore. Questo parametro contiene esattamente un bit dell'enumerazione [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il `dwFlags` parametro contiene esattamente un bit `ASM_CACHE_FLAGS` dall'enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyEnum](iassemblyenum-interface.md)
- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
