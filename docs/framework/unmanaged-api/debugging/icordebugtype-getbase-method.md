---
title: Metodo ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379994"
---
# <a name="icordebugtypegetbase-method"></a>Metodo ICorDebugType::GetBase
Ottiene un puntatore a interfaccia a un oggetto ICorDebugType che rappresenta il tipo di base, se presente, del tipo rappresentato dall'oggetto `ICorDebugType` .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBase`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il tipo di base.  
  
## <a name="remarks"></a>Osservazioni  
 La ricerca del tipo di base per un tipo è utile per implementare funzionalità comuni del debugger, ad esempio la stampa di tutti i campi di un oggetto o delle relative classi padre.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
