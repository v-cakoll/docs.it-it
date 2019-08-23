---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964789"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Le applicazioni che [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ospitano il contenuto tramite PresentationHost. exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost. exe.  
  
## <a name="remarks"></a>Note  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]le applicazioni, ad esempio i Web [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] browser, possono [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] ospitare contenuto, incluso e separato da XAML. Per ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] il contenuto [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] , le applicazioni creano un'istanza del [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Per essere ospitata [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] , crea un'istanza di PresentationHost. exe, che fornisce il [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto ospitato all'host per la visualizzazione nel [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 L'integrazione abilitata `IWpfHostSupport` da consente a PresentationHost. exe di:  
  
- Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.  
  
- Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.  
  
- Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.  
  
> [!NOTE]
> Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.|  
|[FilterInputMessage](filterinputmessage.md)|Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|Per impostazione predefinita, PresentationHost. exe fornisce le interfacce utente per lo stato di distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.|
