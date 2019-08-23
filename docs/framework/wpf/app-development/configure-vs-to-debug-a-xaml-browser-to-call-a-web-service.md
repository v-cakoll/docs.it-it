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
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958682"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="e0a90-102">Procedura: Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web</span><span class="sxs-lookup"><span data-stu-id="e0a90-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="e0a90-103">eseguire in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet.</span><span class="sxs-lookup"><span data-stu-id="e0a90-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="e0a90-104">Questo set di autorizzazioni limita le [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] chiamate al servizio Web solo ai servizi Web che si trovano nel sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0a90-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="e0a90-105">Quando viene [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] eseguito il debug di un oggetto da Visual Studio 2005, tuttavia, non viene considerato lo stesso sito di origine del servizio Web a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e0a90-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="e0a90-106">In questo modo vengono generate eccezioni di sicurezza [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] quando si tenta di chiamare il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e0a90-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="e0a90-107">Tuttavia, è possibile configurare un [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] progetto Visual Studio 2005 per simulare la presenza dello stesso sito di origine del servizio Web chiamato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="e0a90-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="e0a90-108">Ciò consente [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] a di chiamare in modo sicuro il servizio Web senza causare eccezioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e0a90-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="e0a90-109">Configurazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e0a90-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="e0a90-110">Per configurare Visual Studio 2005 per eseguire il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debug di un oggetto che chiama un servizio Web:</span><span class="sxs-lookup"><span data-stu-id="e0a90-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="e0a90-111">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e0a90-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="e0a90-112">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="e0a90-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="e0a90-113">Nella sezione **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e0a90-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="e0a90-114">Nella sezione **Opzioni di avvio** immettere quanto segue nella casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="e0a90-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="e0a90-115">`-debug`  *filename*</span><span class="sxs-lookup"><span data-stu-id="e0a90-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="e0a90-116">Il valore del *nome file* per il parametro **-debug** è il nome file. XBAP; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e0a90-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="e0a90-117">Questa è la configurazione predefinita per le soluzioni create con il modello di progetto di [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="e0a90-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="e0a90-118">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e0a90-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="e0a90-119">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="e0a90-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="e0a90-120">Nella sezione **Opzioni di avvio** aggiungere il parametro della riga di comando seguente alla casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="e0a90-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="e0a90-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="e0a90-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="e0a90-122">Il valore dell' *URL* per il parametro **-debugSecurityZoneURL** è [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] l'oggetto per la posizione che si vuole simulare come sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0a90-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="e0a90-123">Si consideri ad esempio [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] un oggetto che utilizza un servizio Web con [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e0a90-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="e0a90-124">Il sito di origine [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per questo servizio Web è:</span><span class="sxs-lookup"><span data-stu-id="e0a90-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="e0a90-125">Di conseguenza, il parametro e il valore della riga di comando complete **-debugSecurityZoneURL** sono:</span><span class="sxs-lookup"><span data-stu-id="e0a90-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="e0a90-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0a90-126">See also</span></span>

- [<span data-ttu-id="e0a90-127">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e0a90-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
