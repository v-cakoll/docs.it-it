---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 57d9ef87a078655a89a5869a48a1bd16f21b000f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385154"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="04ba8-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="04ba8-102">IWpfHostSupport</span></span>
<span data-ttu-id="04ba8-103">Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto tramite PresentationHost.exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="04ba8-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04ba8-104">Note</span><span class="sxs-lookup"><span data-stu-id="04ba8-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="04ba8-105"> le applicazioni, ad esempio i browser Web possono ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] il contenuto, tra cui [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e separare XAML.</span><span class="sxs-lookup"><span data-stu-id="04ba8-105"> applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="04ba8-106">Per ospitare [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni creano un'istanza del [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="04ba8-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="04ba8-107">Deve essere ospitato [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea un'istanza di PresentationHost.exe, che fornisce l'hosting [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenuto nell'host per la visualizzazione nel [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="04ba8-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="04ba8-108">L'integrazione abilitata da `IWpfHostSupport` consente PresentationHost.exe per:</span><span class="sxs-lookup"><span data-stu-id="04ba8-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
-   <span data-ttu-id="04ba8-109">Individuare e registrare i dispositivi di input non elaborati (Human Interface Devices) che interessata l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="04ba8-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
-   <span data-ttu-id="04ba8-110">Ricevere i messaggi di input dalla registrato i dispositivi di input non elaborati e inoltra i messaggi appropriati per l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="04ba8-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
-   <span data-ttu-id="04ba8-111">Eseguire una query sull'applicazione host per interfacce utente personalizzate di stato e di errore.</span><span class="sxs-lookup"><span data-stu-id="04ba8-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04ba8-112">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="04ba8-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="04ba8-113">Membri</span><span class="sxs-lookup"><span data-stu-id="04ba8-113">Members</span></span>  
  
|<span data-ttu-id="04ba8-114">Membro</span><span class="sxs-lookup"><span data-stu-id="04ba8-114">Member</span></span>|<span data-ttu-id="04ba8-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04ba8-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04ba8-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="04ba8-116">GetRawInputDevices</span></span>](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|<span data-ttu-id="04ba8-117">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="04ba8-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="04ba8-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="04ba8-118">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|<span data-ttu-id="04ba8-119">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="04ba8-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="04ba8-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="04ba8-120">GetCustomUI</span></span>](../../../../docs/framework/wpf/app-development/getcustomui.md)|<span data-ttu-id="04ba8-121">Per impostazione predefinita, PresentationHost.exe fornisce il proprio avanzamento della distribuzione e l'errore di distribuzione interfacce utente che vengono visualizzate quando si distribuisce contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="04ba8-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
