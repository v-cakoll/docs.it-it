---
title: Funzione LoadFromHistory-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727938"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Funzione LoadFromHistory (riferimenti alle API non gestite WPF)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pHistoryStream  
 Puntatore a un flusso di informazioni sulla cronologia.  
  
 pBindCtx  
 Puntatore a un contesto di associazione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)
