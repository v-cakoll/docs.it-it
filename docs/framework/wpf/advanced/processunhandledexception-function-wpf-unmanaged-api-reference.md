---
title: Funzione ProcessUnhandledException-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743915"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>Funzione ProcessUnhandledException (riferimenti alle API non gestite WPF)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione delle eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>Parametri  
 errorMsg  
 Messaggio di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)
