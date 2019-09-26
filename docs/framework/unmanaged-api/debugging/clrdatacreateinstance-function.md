---
title: Funzione CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d44f9b5dc42147959d3f1d127a64d39258f515
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274273"
---
# <a name="clrdatacreateinstance-function"></a>Funzione CLRDataCreateInstance
Crea un oggetto interfaccia per l'elemento di destinazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iid`  
 in Identificatore dell'interfaccia di cui creare un'istanza.  
  
 `target`  
 in Puntatore a un oggetto [ICLRDataTarget](iclrdatatarget-interface.md) implementato dall'utente che rappresenta l'elemento di destinazione per il quale creare l'oggetto interfaccia.  
  
 `iface`  
 out Puntatore all'indirizzo dell'oggetto interfaccia restituito.  
  
## <a name="remarks"></a>Note  
 L' `ICLRDataTarget` oggetto viene implementato dal writer dell'applicazione di debug. L'implementazione dipende dal tipo di elemento di destinazione rappresentato. L'elemento di destinazione può essere un processo, un dump della memoria, un computer remoto e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](debugging-global-static-functions.md)
