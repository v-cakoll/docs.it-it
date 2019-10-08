---
title: "Procedura: Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web"
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 8ec278f2bc66d9b40786123af684f6468b6a9d83
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005666"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="16de0-102">Procedura: Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web</span><span class="sxs-lookup"><span data-stu-id="16de0-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="16de0-103">vengono eseguiti in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet.</span><span class="sxs-lookup"><span data-stu-id="16de0-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="16de0-104">Questo set di autorizzazioni limita le chiamate al servizio Web solo ai servizi Web che si trovano nel sito di origine dell'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16de0-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="16de0-105">Quando si esegue il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] da Visual Studio 2005, tuttavia, non si considera lo stesso sito di origine del servizio Web a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="16de0-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="16de0-106">In questo modo vengono generate eccezioni di sicurezza quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tenta di chiamare il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="16de0-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="16de0-107">Tuttavia, è possibile configurare un progetto Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] per simulare la presenza dello stesso sito di origine del servizio Web chiamato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="16de0-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="16de0-108">Questo consente a [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] di chiamare in modo sicuro il servizio Web senza causare eccezioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16de0-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="16de0-109">Configurazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="16de0-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="16de0-110">Per configurare Visual Studio 2005 per eseguire il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che chiama un servizio Web:</span><span class="sxs-lookup"><span data-stu-id="16de0-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="16de0-111">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="16de0-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="16de0-112">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="16de0-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="16de0-113">Nella sezione **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="16de0-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="16de0-114">Nella sezione **Opzioni di avvio** immettere quanto segue nella casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="16de0-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="16de0-115">*nome file* `-debug`</span><span class="sxs-lookup"><span data-stu-id="16de0-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="16de0-116">Il valore del *nome file* per il parametro **-debug** è il nome file. XBAP; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="16de0-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="16de0-117">Questa è la configurazione predefinita per le soluzioni create con il modello di progetto di Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16de0-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="16de0-118">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="16de0-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="16de0-119">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="16de0-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="16de0-120">Nella sezione **Opzioni di avvio** aggiungere il parametro della riga di comando seguente alla casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="16de0-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="16de0-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="16de0-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="16de0-122">Il valore dell' *URL* per il parametro **-debugSecurityZoneURL** è il [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] per il percorso che si vuole simulare come il sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="16de0-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="16de0-123">Si consideri ad esempio un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che usa un servizio Web con l'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="16de0-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="16de0-124">L'URL del sito di origine per questo servizio Web è:</span><span class="sxs-lookup"><span data-stu-id="16de0-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="16de0-125">Di conseguenza, il parametro e il valore della riga di comando complete **-debugSecurityZoneURL** sono:</span><span class="sxs-lookup"><span data-stu-id="16de0-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="16de0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16de0-126">See also</span></span>

- [<span data-ttu-id="16de0-127">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="16de0-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
