---
title: Funzione CreateIDispatchSTAForwarder-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738039"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Funzione CreateIDispatchSTAForwarder (riferimenti alle API non gestite WPF)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di thread e finestre.  
  
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
 Puntatore a un'interfaccia `IDispatch`.  
  
 ppForwarder  
 Puntatore all'indirizzo di un'interfaccia `IDispatch`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)
