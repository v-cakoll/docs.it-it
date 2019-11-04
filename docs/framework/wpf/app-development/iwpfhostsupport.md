---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423643"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="6f0bf-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="6f0bf-102">IWpfHostSupport</span></span>
<span data-ttu-id="6f0bf-103">Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto tramite PresentationHost. exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f0bf-104">Note</span><span class="sxs-lookup"><span data-stu-id="6f0bf-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] <span data-ttu-id="6f0bf-105">applicazioni quali i Web browser possono ospitare contenuto WPF, incluse le applicazioni browser XAML (XBAP) e il codice XAML separato.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-105">applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="6f0bf-106">Per ospitare il contenuto WPF, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] le applicazioni creano un'istanza del [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="6f0bf-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="6f0bf-107">Per essere ospitata, WPF crea un'istanza di PresentationHost. exe, che fornisce il contenuto WPF ospitato all'host per la visualizzazione nel [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="6f0bf-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="6f0bf-108">L'integrazione abilitata da `IWpfHostSupport` consente a PresentationHost. exe di:</span><span class="sxs-lookup"><span data-stu-id="6f0bf-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="6f0bf-109">Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="6f0bf-110">Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="6f0bf-111">Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f0bf-112">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="6f0bf-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="6f0bf-113">Members</span><span class="sxs-lookup"><span data-stu-id="6f0bf-113">Members</span></span>  
  
|<span data-ttu-id="6f0bf-114">Member</span><span class="sxs-lookup"><span data-stu-id="6f0bf-114">Member</span></span>|<span data-ttu-id="6f0bf-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f0bf-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f0bf-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="6f0bf-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="6f0bf-117">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="6f0bf-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="6f0bf-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="6f0bf-119">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="6f0bf-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="6f0bf-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="6f0bf-121">Per impostazione predefinita, PresentationHost. exe fornisce le interfacce utente per lo stato di distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="6f0bf-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
