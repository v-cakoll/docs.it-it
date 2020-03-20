---
title: Funzione CreateIDispatchSTAForwarder - Riferimento all'API non gestita WPFCreateIDispatchSTAForwarder Function - WPF unmanaged API reference
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174719"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di thread e finestre.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parametri  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 pDispatchDelegate  
 Puntatore a `IDispatch` un'interfaccia.  
  
 ppForwarder (ppForwarder)  
 Puntatore all'indirizzo `IDispatch` di un'interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)
