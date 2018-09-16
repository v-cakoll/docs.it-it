---
title: Configurazione di Internet Information Services 7.0 per Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 13fd068f7a058a0fbf4e15fc99a8de91671fb2d5
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664618"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="32e53-102">Configurazione di Internet Information Services 7.0 per Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="32e53-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>

<span data-ttu-id="32e53-103">Internet Information Services (IIS) 7.0 dispone di una progettazione modulare che consente di installare in modo selettivo i componenti necessari.</span><span class="sxs-lookup"><span data-stu-id="32e53-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="32e53-104">Questa progettazione si basa sulla nuova tecnologia di componentizzazione basata su manifesti introdotta in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32e53-104">This design is based on the new manifest-driven componentization technology introduced in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="32e53-105">Sono presenti più di 40 componenti delle caratteristiche autonoma di IIS 7.0 che possono essere installati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="32e53-105">There are more than 40 standalone feature components of IIS 7.0 that can be installed independently.</span></span> <span data-ttu-id="32e53-106">I professionisti IT possono così personalizzare con facilità l'installazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="32e53-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="32e53-107">In questo argomento illustra come configurare IIS 7.0 per l'uso con Windows Communication Foundation (WCF) e determinare quali componenti sono necessari.</span><span class="sxs-lookup"><span data-stu-id="32e53-107">This topic discusses how to configure IIS 7.0 for use with Windows Communication Foundation (WCF) and determine which components are required.</span></span>

## <a name="minimal-installation-installing-was"></a><span data-ttu-id="32e53-108">Installazione minima: installazione di WAS</span><span class="sxs-lookup"><span data-stu-id="32e53-108">Minimal Installation: Installing WAS</span></span>
 <span data-ttu-id="32e53-109">L'installazione minima dell'intero pacchetto IIS 7.0 consiste nell'installare il servizio di attivazione processo Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="32e53-109">The minimal installation of the whole IIS 7.0 package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="32e53-110">È stato è una funzionalità autonoma ed è la sola funzionalità di IIS 7.0 che è disponibile per tutti i [!INCLUDE[wv](../../../../includes/wv-md.md)] i sistemi operativi (Home Basic, Home Premium, Business e Ultimate ed Enterprise).</span><span class="sxs-lookup"><span data-stu-id="32e53-110">WAS is a standalone feature and it is the only feature from the IIS 7.0 that is available for all [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>

 <span data-ttu-id="32e53-111">Dal Pannello di controllo, fare clic su **i programmi** e quindi fare clic su **o disattivazione delle funzionalità Windows attivare** elencata sotto **programmi e funzionalità**, il componente WAS è riportato di elenco come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="32e53-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>

 <span data-ttu-id="32e53-112">![Attivare le funzionalità o della finestra disattivata](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="32e53-112">![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>

 <span data-ttu-id="32e53-113">Questa funzionalità presenta i sottocomponenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="32e53-113">This feature has the following sub-components:</span></span>

-   <span data-ttu-id="32e53-114">Ambiente .NET</span><span class="sxs-lookup"><span data-stu-id="32e53-114">.NET Environment</span></span>

-   <span data-ttu-id="32e53-115">API di configurazione</span><span class="sxs-lookup"><span data-stu-id="32e53-115">Configuration APIs</span></span>

-   <span data-ttu-id="32e53-116">Modello di processo</span><span class="sxs-lookup"><span data-stu-id="32e53-116">Process Model</span></span>

 <span data-ttu-id="32e53-117">Se si seleziona solo il nodo radice di WAS, il **modello di processo** sottonodo viene selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="32e53-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="32e53-118">Si noti che con questa installazione verrà installato solo il servizio WAS poiché non è disponibile alcun supporto per un server Web.</span><span class="sxs-lookup"><span data-stu-id="32e53-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>

 <span data-ttu-id="32e53-119">Per rendere tutte le operazioni di applicazione ASP.NET o WCF, controllare la **ambiente .NET** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="32e53-119">To make WCF or any ASP.NET application work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="32e53-120">Ciò significa che tutti i componenti WAS sono obbligatori per rendere WCF e ASP.NET in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="32e53-120">This means that all of WAS components are required to make WCF and ASP.NET to work well.</span></span> <span data-ttu-id="32e53-121">Questi verranno selezionati automaticamente una volta installati tali componenti.</span><span class="sxs-lookup"><span data-stu-id="32e53-121">These are automatically checked once you install any of those components.</span></span>

## <a name="iis-70-default-installation"></a><span data-ttu-id="32e53-122">IIS 7.0: installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="32e53-122">IIS 7.0: Default Installation</span></span>
 <span data-ttu-id="32e53-123">Controllando il **Internet Information Services** funzionalità, alcuni dei nodi secondari vengono contrassegnati automaticamente come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="32e53-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>

 <span data-ttu-id="32e53-124">![Impostazioni predefinite per le funzionalità di IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="32e53-124">![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>

 <span data-ttu-id="32e53-125">Questo è l'installazione predefinita di IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="32e53-125">This is the default installation of IIS 7.0.</span></span> <span data-ttu-id="32e53-126">Con questa installazione, è possibile utilizzare IIS 7.0 per gestire il contenuto statico (ad esempio pagine HTML e altro contenuto).</span><span class="sxs-lookup"><span data-stu-id="32e53-126">With this installation, you can use IIS 7.0 to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="32e53-127">Tuttavia, non è possibile eseguire le applicazioni ASP.NET o CGI o ospitare servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="32e53-127">However, you cannot run ASP.NET or CGI applications or host WCF services.</span></span>

## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="32e53-128">IIS 7.0: installazione con supporto ASP.NET</span><span class="sxs-lookup"><span data-stu-id="32e53-128">IIS 7.0: Installation with ASP.NET Support</span></span>
 <span data-ttu-id="32e53-129">È necessario installare ASP.NET per il funzionamento di ASP.NET in IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="32e53-129">You must install ASP.NET to make ASP.NET work on IIS 7.0.</span></span> <span data-ttu-id="32e53-130">Dopo aver controllato **ASP.NET**, la schermata dovrebbe essere simile alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="32e53-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>

 <span data-ttu-id="32e53-131">![Asp.NET le impostazioni necessarie](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="32e53-131">![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>

 <span data-ttu-id="32e53-132">Questo è l'ambiente minimo per le applicazioni ASP.NET sia WCF lavorare in IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="32e53-132">This is the minimal environment for both WCF and ASP.NET applications to work in IIS 7.0.</span></span>

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="32e53-133">IIS 7.0: installazione con componenti compatibilità gestione IIS 6.0</span><span class="sxs-lookup"><span data-stu-id="32e53-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>
 <span data-ttu-id="32e53-134">Quando si installa IIS 7.0 in un sistema con Visual Studio 2005 o alcuni altri script di automazione o gli strumenti (ad esempio Adsutil. vbs) che consentono di configurare le applicazioni virtuali che usano API della Metabase di IIS 6.0, assicurarsi di selezionare IIS 6.0 **gli strumenti di Scripting**.</span><span class="sxs-lookup"><span data-stu-id="32e53-134">When installing IIS 7.0 on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use IIS 6.0 Metabase API, ensure that you check the IIS 6.0 **Scripting Tools**.</span></span> <span data-ttu-id="32e53-135">Si verifica automaticamente gli altri sottonodi di IIS 6.0 **compatibilità gestione**.</span><span class="sxs-lookup"><span data-stu-id="32e53-135">This automatically checks the other sub-nodes of IIS 6.0 **Management Compatibility**.</span></span> <span data-ttu-id="32e53-136">La figura seguente mostra la schermata dopo questa operazione viene eseguita:</span><span class="sxs-lookup"><span data-stu-id="32e53-136">The following illustration shows the screen after this is done:</span></span>

 <span data-ttu-id="32e53-137">![Impostazioni di compatibilità IIS 6.0 Management](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="32e53-137">![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>

 <span data-ttu-id="32e53-138">Con questa installazione, sono disponibili tutte le operazioni necessarie per usare le funzionalità di IIS 7.0, ASP.NET e WCF e gli esempi disponibili sul Web.</span><span class="sxs-lookup"><span data-stu-id="32e53-138">With this installation, you have everything required to use IIS 7.0, ASP.NET and WCF features and samples available on the Web.</span></span>

## <a name="request-limits"></a><span data-ttu-id="32e53-139">Limiti di richiesta.</span><span class="sxs-lookup"><span data-stu-id="32e53-139">Request Limits</span></span>
 <span data-ttu-id="32e53-140">In [!INCLUDE[wv](../../../../includes/wv-md.md)] con IIS 7 il valore predefinito delle impostazioni `maxUri` e `maxQueryStringSize` è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="32e53-140">On [!INCLUDE[wv](../../../../includes/wv-md.md)] with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="32e53-141">Per impostazione predefinita, il filtro di richiesta in IIS 7.0 consente una lunghezza dell'URL di 4096 caratteri e una lunghezza della stringa di query di 2048 caratteri.</span><span class="sxs-lookup"><span data-stu-id="32e53-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="32e53-142">Per modificare questi valori predefiniti, aggiungere il codice XML seguente al file App.config:</span><span class="sxs-lookup"><span data-stu-id="32e53-142">To change these defaults add the following XML to your App.config file.</span></span>

 `<system.webServer>`

 `<security>`

 `<requestFiltering>`

 `<requestLimits maxUrl="8192" maxQueryString="8192" />`

 `</requestFiltering>`

 `</security>`

 `</system.webServer>`

## <a name="see-also"></a><span data-ttu-id="32e53-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e53-143">See Also</span></span>

- [<span data-ttu-id="32e53-144">Architettura di attivazione di WAS</span><span class="sxs-lookup"><span data-stu-id="32e53-144">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [<span data-ttu-id="32e53-145">Configurazione di WAS per l'uso con WCF</span><span class="sxs-lookup"><span data-stu-id="32e53-145">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="32e53-146">Procedura: Installare e configurare componenti di attivazione WCF</span><span class="sxs-lookup"><span data-stu-id="32e53-146">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [<span data-ttu-id="32e53-147">Windows Server AppFabric con funzionalità di Hosting</span><span class="sxs-lookup"><span data-stu-id="32e53-147">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
