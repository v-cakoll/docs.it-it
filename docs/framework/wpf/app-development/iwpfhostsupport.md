---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 85309e46403b2f22f9afb760d4c4ae370c39246b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004099"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="29fb7-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="29fb7-102">IWpfHostSupport</span></span>
<span data-ttu-id="29fb7-103">Le applicazioni che ospitano contenuto [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] tramite PresentationHost. exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="29fb7-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29fb7-104">Note</span><span class="sxs-lookup"><span data-stu-id="29fb7-104">Remarks</span></span>  
 <span data-ttu-id="29fb7-105">le applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], ad esempio i Web browser, possono ospitare contenuto WPF, tra cui [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e XAML separato.</span><span class="sxs-lookup"><span data-stu-id="29fb7-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="29fb7-106">Per ospitare il contenuto WPF, le applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] creano un'istanza del [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="29fb7-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="29fb7-107">Per essere ospitata, WPF crea un'istanza di PresentationHost. exe, che fornisce il contenuto WPF ospitato all'host per la visualizzazione nel [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="29fb7-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="29fb7-108">L'integrazione abilitata da `IWpfHostSupport` consente a PresentationHost. exe di:</span><span class="sxs-lookup"><span data-stu-id="29fb7-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="29fb7-109">Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="29fb7-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="29fb7-110">Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="29fb7-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="29fb7-111">Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.</span><span class="sxs-lookup"><span data-stu-id="29fb7-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29fb7-112">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="29fb7-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="29fb7-113">Members</span><span class="sxs-lookup"><span data-stu-id="29fb7-113">Members</span></span>  
  
|<span data-ttu-id="29fb7-114">Member</span><span class="sxs-lookup"><span data-stu-id="29fb7-114">Member</span></span>|<span data-ttu-id="29fb7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29fb7-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29fb7-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="29fb7-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="29fb7-117">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="29fb7-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="29fb7-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="29fb7-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="29fb7-119">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="29fb7-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="29fb7-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="29fb7-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="29fb7-121">Per impostazione predefinita, PresentationHost. exe fornisce le interfacce utente per lo stato di distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="29fb7-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
