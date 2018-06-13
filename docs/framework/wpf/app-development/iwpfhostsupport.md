---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 51964358d27a16d9840e29be06c11f57de2fad23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548194"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto tramite PresentationHost.exe implementare questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost.exe.  
  
## <a name="remarks"></a>Note  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni, ad esempio i browser Web possono ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] il contenuto, tra cui [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e XAML separato. Host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni di creare un'istanza del [controllo WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911). Deve essere ospitato, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea un'istanza di PresentationHost.exe, che fornisce il contenuto [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto nell'host per la visualizzazione nel [controllo WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 L'integrazione abilitata da `IWpfHostSupport` consente PresentationHost.exe per:  
  
-   Individuare e registrare i dispositivi di input non elaborati (Human Interface Device) che interessata l'applicazione host.  
  
-   Ricevere messaggi di input dalla registrato i dispositivi di input non elaborato e inoltra i messaggi appropriati per l'applicazione host.  
  
-   L'applicazione host per interfacce utente personalizzate di stato e di errore di query.  
  
> [!NOTE]
>  Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|Per impostazione predefinita, PresentationHost.exe fornisce il proprio stato distribuzione e un errore di distribuzione interfacce utente che vengono visualizzate quando si distribuisce contenuto WPF.|
