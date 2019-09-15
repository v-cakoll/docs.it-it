---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1453946766e33843ae9e56f7a7f4dbf1678b81b5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991391"
---
# <a name="filterinputmessage"></a>FilterInputMessage
Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
## <a name="parameters"></a>Parametri  
 `pMsg`  
  
 [in] Messaggio WM_INPUT inviato alla finestra che sta ricevendo l'input non elaborato.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT:  
  
 S_OK: il filtro non ha elaborato il messaggio e l'elaborazione può proseguire.  
  
 S_FALSE: il filtro ha elaborato questo messaggio e non viene eseguita alcuna ulteriore elaborazione.  
  
 E_NOTIMPL: se viene restituito questo valore, [FilterInputMessage](filterinputmessage.md) non viene chiamato nuovamente. È possibile che venga restituito da un'applicazione host interessata solo a fornire interfacce utente personalizzate di stato ed errore a PresentationHost.exe e non a ricevere messaggi di input non elaborato da PresentationHost.exe.  
  
## <a name="remarks"></a>Note  
 PresentationHost.exe è la destinazione di vari dispositivi di input non elaborato, tra cui tastiere, mouse e telecomandi. In alcuni casi, il comportamento nell'applicazione host dipende dall'input che, in caso contrario, verrebbe usato da PresentationHost.exe. Ad esempio, la visualizzazione di specifici elementi dell'interfaccia utente da parte di un'applicazione host può dipendere dalla ricezione di determinati messaggi di input.  
  
 Per consentire all'applicazione host di ricevere i messaggi di input necessari per fornire questi comportamenti, PresentationHost. exe invia i messaggi di input non elaborati appropriati all'applicazione ospitata chiamando [FilterInputMessage](filterinputmessage.md).  
  
 L'applicazione ospitata riceve i messaggi di input non elaborati eseguendo la registrazione con il set di dispositivi di input non elaborati (Human Interface Device) restituiti da [GetRawInputDevices](getrawinputdevices.md).  
  
## <a name="see-also"></a>Vedere anche

- [Messaggio WM_INPUT](/windows/desktop/inputdev/wm-input)
