---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 074167111b78edc517dda019465260d0acd54737
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006694"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto tramite PresentationHost.exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost.exe.  
  
## <a name="remarks"></a>Note  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni, ad esempio i browser Web possono ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] il contenuto, tra cui [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare XAML. Per ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni creano un'istanza del [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Deve essere ospitato [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea un'istanza di PresentationHost.exe, che fornisce l'hosting [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto nell'host per la visualizzazione nel [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 L'integrazione abilitata da `IWpfHostSupport` consente PresentationHost.exe per:  
  
- Individuare e registrare i dispositivi di input non elaborati (Human Interface Devices) che interessata l'applicazione host.  
  
- Ricevere i messaggi di input dalla registrato i dispositivi di input non elaborati e inoltra i messaggi appropriati per l'applicazione host.  
  
- Eseguire una query sull'applicazione host per interfacce utente personalizzate di stato e di errore.  
  
> [!NOTE]
>  Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.|  
|[FilterInputMessage](filterinputmessage.md)|Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|Per impostazione predefinita, PresentationHost.exe fornisce il proprio avanzamento della distribuzione e l'errore di distribuzione interfacce utente che vengono visualizzate quando si distribuisce contenuto WPF.|
