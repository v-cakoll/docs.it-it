---
title: "Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web"
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 948a730185650cb3449202503a049e9caff7c4bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547499"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="70362-102">Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web</span><span class="sxs-lookup"><span data-stu-id="70362-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="70362-103"> eseguito all'interno di una sandbox di sicurezza con attendibilità parziale che è limitata per il set di autorizzazioni area Internet.</span><span class="sxs-lookup"><span data-stu-id="70362-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="70362-104">Questo set di autorizzazioni limita le chiamate di servizio Web per servizi Web che si trovano nel [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70362-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="70362-105">Quando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è sottoposta a debug da [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], tuttavia, non è considerato hanno lo stesso sito di origine come servizio Web a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="70362-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="70362-106">Eccezioni di sicurezza questo cause per essere generato quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tenta di chiamare il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="70362-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="70362-107">Tuttavia, un [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] progetto può essere configurato per simulare la presenza di stesso sito di origine il servizio Web chiamato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="70362-107">However, a [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="70362-108">In questo modo il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per chiamare il servizio Web senza provocare eccezioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="70362-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>  
  
## <a name="configuring-visual-studio"></a><span data-ttu-id="70362-109">Configurazione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="70362-109">Configuring Visual Studio</span></span>  
 <span data-ttu-id="70362-110">Per configurare [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] eseguire il debug di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che chiama un servizio Web:</span><span class="sxs-lookup"><span data-stu-id="70362-110">To configure [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>  
  
1.  <span data-ttu-id="70362-111">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="70362-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="70362-112">Nel **progettazione**, fare clic su di **Debug** scheda.</span><span class="sxs-lookup"><span data-stu-id="70362-112">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="70362-113">Nel **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="70362-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  <span data-ttu-id="70362-114">Nel **opzioni di avvio** sezione, immettere quanto segue nel **argomenti della riga di comando** casella di testo:</span><span class="sxs-lookup"><span data-stu-id="70362-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="70362-115">`-debug`  *nome file*</span><span class="sxs-lookup"><span data-stu-id="70362-115">`-debug`  *filename*</span></span>  
  
     <span data-ttu-id="70362-116">Il *filename* valore per il **-debug** parametro è il nome del file xbap, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70362-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  <span data-ttu-id="70362-117">Questa è la configurazione predefinita per le soluzioni create con la [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="70362-117">This is the default configuration for solutions that are created with the [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>  
  
1.  <span data-ttu-id="70362-118">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="70362-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="70362-119">Nel **progettazione**, fare clic su di **Debug** scheda.</span><span class="sxs-lookup"><span data-stu-id="70362-119">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="70362-120">Nel **opzioni di avvio** sezione, aggiungere il parametro della riga di comando seguente per il **argomenti della riga di comando** casella di testo:</span><span class="sxs-lookup"><span data-stu-id="70362-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="70362-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="70362-121">`-debugSecurityZoneURL`  *URL*</span></span>  
  
     <span data-ttu-id="70362-122">Il *URL* valore per il **- debugSecurityZoneURL** parametro è il [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] per il percorso che si desidera simulare come sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70362-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>  
  
 <span data-ttu-id="70362-123">Ad esempio, si consideri un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che utilizza un servizio Web con il codice seguente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="70362-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 <span data-ttu-id="70362-124">Il sito di origine [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per questo sito Web servizio è:</span><span class="sxs-lookup"><span data-stu-id="70362-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>  
  
 `http://services.msdn.microsoft.com`  
  
 <span data-ttu-id="70362-125">Di conseguenza, l'intero **- debugSecurityZoneURL** parametro della riga di comando e il valore è:</span><span class="sxs-lookup"><span data-stu-id="70362-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a><span data-ttu-id="70362-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70362-126">See Also</span></span>  
 [<span data-ttu-id="70362-127">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="70362-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
