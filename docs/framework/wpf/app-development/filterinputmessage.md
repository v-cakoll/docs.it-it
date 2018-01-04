---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e76f9863b68d5c7c34bca8adc872210527d6c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="filterinputmessage"></a>FilterInputMessage
Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pMsg`  
  
 [in] Messaggio WM_INPUT inviato alla finestra che sta ricevendo l'input non elaborato.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT:  
  
 S_OK: il filtro non ha elaborato il messaggio e l'elaborazione può proseguire.  
  
 S_FALSE: il filtro ha elaborato questo messaggio e non viene eseguita alcuna ulteriore elaborazione.  
  
 E_NOTIMPL: se questo valore viene restituito, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) non viene più chiamato. È possibile che venga restituito da un'applicazione host interessata solo a fornire interfacce utente personalizzate di stato ed errore a PresentationHost.exe e non a ricevere messaggi di input non elaborato da PresentationHost.exe.  
  
## <a name="remarks"></a>Note  
 PresentationHost.exe è la destinazione di vari dispositivi di input non elaborato, tra cui tastiere, mouse e telecomandi. In alcuni casi, il comportamento nell'applicazione host dipende dall'input che, in caso contrario, verrebbe usato da PresentationHost.exe. Ad esempio, la visualizzazione di specifici elementi dell'interfaccia utente da parte di un'applicazione host può dipendere dalla ricezione di determinati messaggi di input.  
  
 Per consentire all'applicazione host di ricevere i messaggi di input necessari per questi comportamenti, PresentationHost.exe inoltra i messaggi di input non elaborati adatti per l'applicazione ospitata chiamando [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 L'applicazione ospitata riceve i messaggi di input non elaborati tramite la registrazione con il set di dispositivi inpui non elaborati (Human Interface Device) restituito da [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Notifica WM_INPUT](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
