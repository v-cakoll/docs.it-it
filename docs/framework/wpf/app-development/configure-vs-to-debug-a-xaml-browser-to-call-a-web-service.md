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
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460897"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="e1a4b-102">Procedura: configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web</span><span class="sxs-lookup"><span data-stu-id="e1a4b-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="e1a4b-103">Le applicazioni browser XAML (XBAPs) vengono eseguite in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="e1a4b-104">Questo set di autorizzazioni limita le chiamate al servizio Web solo ai servizi Web che si trovano nel sito di origine dell'applicazione XBAP.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="e1a4b-105">Quando si esegue il debug di un'applicazione XBAP da Visual Studio 2005, tuttavia, non si considera lo stesso sito di origine del servizio Web a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="e1a4b-106">In questo modo vengono generate eccezioni di sicurezza quando l'applicazione XBAP tenta di chiamare il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="e1a4b-107">Tuttavia, è possibile configurare un progetto di applicazione browser XAML (WPF) di Visual Studio 2005 per simulare la presenza dello stesso sito di origine del servizio Web chiamato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-107">However, a Visual Studio 2005 XAML Browser Application (WPF) project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="e1a4b-108">Ciò consente all'applicazione XBAP di chiamare in modo sicuro il servizio Web senza causare eccezioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="e1a4b-109">Configurazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e1a4b-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="e1a4b-110">Per configurare Visual Studio 2005 per eseguire il debug di un'applicazione XBAP che chiama un servizio Web:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="e1a4b-111">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="e1a4b-112">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="e1a4b-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="e1a4b-113">Nella sezione **azione di avvio** selezionare **Avvia programma esterno** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="e1a4b-114">Nella sezione **Opzioni di avvio** immettere quanto segue nella casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="e1a4b-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="e1a4b-115">*nome file* `-debug`</span><span class="sxs-lookup"><span data-stu-id="e1a4b-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="e1a4b-116">Il valore del *nome file* per il parametro **-debug** è il nome file. XBAP; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="e1a4b-117">Si tratta della configurazione predefinita per le soluzioni create con il modello di progetto applicazione browser XAML di Visual Studio 2005 (WPF).</span><span class="sxs-lookup"><span data-stu-id="e1a4b-117">This is the default configuration for solutions that are created with the Visual Studio 2005 XAML Browser Application (WPF) project template.</span></span>

1. <span data-ttu-id="e1a4b-118">Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="e1a4b-119">In **Progettazione progetti**fare clic sulla scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="e1a4b-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="e1a4b-120">Nella sezione **Opzioni di avvio** aggiungere il parametro della riga di comando seguente alla casella di testo **argomenti della riga di comando** :</span><span class="sxs-lookup"><span data-stu-id="e1a4b-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="e1a4b-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="e1a4b-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="e1a4b-122">Il valore *URL* per il parametro **-DEBUGSECURITYZONEURL** è l'URL per la posizione che si vuole simulare come sito di origine dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1a4b-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="e1a4b-123">Si consideri ad esempio un'applicazione browser XAML (XBAP) che usa un servizio Web con l'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="e1a4b-124">L'URL del sito di origine per questo servizio Web è:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="e1a4b-125">Di conseguenza, il parametro e il valore della riga di comando complete **-debugSecurityZoneURL** sono:</span><span class="sxs-lookup"><span data-stu-id="e1a4b-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="e1a4b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1a4b-126">See also</span></span>

- [<span data-ttu-id="e1a4b-127">Host WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e1a4b-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
