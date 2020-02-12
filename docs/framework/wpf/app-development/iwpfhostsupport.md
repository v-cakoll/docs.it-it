---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: e3edd7f7080562d03453898dba7a9326561803b5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124195"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto tramite PresentationHost. exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost. exe.  
  
## <a name="remarks"></a>Osservazioni  
 Le applicazioni Win32 quali i Web browser possono ospitare contenuto WPF, incluse le applicazioni browser XAML (XBAP) e il codice XAML separato. Per ospitare il contenuto WPF, le applicazioni Win32 creano un'istanza del [controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)). Per essere ospitata, WPF crea un'istanza di PresentationHost. exe, che fornisce il contenuto WPF ospitato all'host per la visualizzazione nel [controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
 L'integrazione abilitata da `IWpfHostSupport` consente a PresentationHost. exe di:  
  
- Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.  
  
- Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.  
  
- Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.  
  
> [!NOTE]
> Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.|  
|[FilterInputMessage](filterinputmessage.md)|Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|Per impostazione predefinita, PresentationHost. exe fornisce le interfacce utente per lo stato di distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.|
