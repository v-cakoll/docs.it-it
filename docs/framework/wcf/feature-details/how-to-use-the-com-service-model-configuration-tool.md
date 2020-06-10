---
title: 'Procedura: usare lo strumento di configurazione del modello di servizi di COM+'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: f9e761bafd84726b51a2010a932c68c67c37f899
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595284"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a><span data-ttu-id="787d7-102">Procedura: usare lo strumento di configurazione del modello di servizi di COM+</span><span class="sxs-lookup"><span data-stu-id="787d7-102">How to: Use the COM+ Service Model Configuration Tool</span></span>
<span data-ttu-id="787d7-103">Dopo aver selezionato una modalità di hosting appropriata, utilizzare lo strumento della riga di comando per la configurazione del modello di servizi COM+ (ComSvcConfig.exe) per configurare le interfacce dell'applicazione da esporre come servizi Web.</span><span class="sxs-lookup"><span data-stu-id="787d7-103">Once you have selected an appropriate hosting mode, use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that will be exposed as Web services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="787d7-104">Per eseguire le attività seguenti è necessario disporre di diritti amministrativi sul computer.</span><span class="sxs-lookup"><span data-stu-id="787d7-104">You must be an administrator on the machine to perform any of the following tasks.</span></span>  
  
 <span data-ttu-id="787d7-105">Quando si utilizza ComSvcConfig.exe su un computer con Windows 7, attenersi alla procedura riportata di seguito per configurare un servizio Web al fine di utilizzare l'ultima versione del modello di servizi (attualmente v4.5):</span><span class="sxs-lookup"><span data-stu-id="787d7-105">When using ComSvcConfig.exe on a Windows 7 machine to configure a web service to use the latest service model version (currently v4.5), perform the following steps:</span></span>  
  
1. <span data-ttu-id="787d7-106">Impostare la chiave del registro `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` di sistema su un valore DWORD pari a 0x00000001</span><span class="sxs-lookup"><span data-stu-id="787d7-106">Set the registry key  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` to a DWORD value of 0x00000001</span></span>  
  
2. <span data-ttu-id="787d7-107">Eseguire comsvcconfig.exe</span><span class="sxs-lookup"><span data-stu-id="787d7-107">Run comsvcconfig.exe</span></span>  
  
3. <span data-ttu-id="787d7-108">Ripristinare la chiave del Registro di sistema aggiunta nel passaggio 1 sul valore originale o eliminarla se non esiste.</span><span class="sxs-lookup"><span data-stu-id="787d7-108">Revert the registry key added in step 1 back to its original value, or delete it if did not exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="787d7-109">Il ripristino di questa chiave del Registro di sistema è importante.</span><span class="sxs-lookup"><span data-stu-id="787d7-109">Reverting this registry key is important.</span></span> <span data-ttu-id="787d7-110">Si tratta di una chiave di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="787d7-110">This is a compatibility key.</span></span> <span data-ttu-id="787d7-111">Se non si ripristina, questa modifica può causare problemi ad altre applicazioni .NET in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="787d7-111">Not reverting this change may cause issues with other .NET applications running on the machine).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="787d7-112">Quando si usa ComSvcConfig. exe/install in un computer con Windows 8, viene visualizzata una finestra di dialogo che indica che l'app nel PC necessita della funzionalità di Windows seguente: .NET Framework 3,5 (include .NET 2,0 e .NET 3,0 "se .NET Framework 3,5 non è installato.</span><span class="sxs-lookup"><span data-stu-id="787d7-112">When using ComSvcConfig.exe  /install on a Windows 8 machine a dialog is displayed stating "An app on your PC needs the following Windows feature: .NET Framework 3.5 (includes .NET 2.0 and .NET 3.0" if .NET Framework 3.5 is not installed.</span></span> <span data-ttu-id="787d7-113">Questa finestra di dialogo può essere ignorata.</span><span class="sxs-lookup"><span data-stu-id="787d7-113">This dialog may be ignored.</span></span> <span data-ttu-id="787d7-114">In alternativa è possibile impostare la chiave del Registro di sistema OnlyUseLatestCLR su un valore DWORD di 0x00000001</span><span class="sxs-lookup"><span data-stu-id="787d7-114">Alternatively you can sed the OnlyUseLatestCLR registry key to a DWORD value of 0x00000001</span></span>  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="787d7-115">Per aggiungere un'interfaccia al set di interfacce esposte come servizi Web mediante la modalità di hosting COM+</span><span class="sxs-lookup"><span data-stu-id="787d7-115">To add an interface to the set of interfaces exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="787d7-116">Eseguire ComSvcConfig utilizzando le opzioni `/install` e `/hosting:complus`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-116">Run ComSvcConfig using the `/install` and `/hosting:complus` options, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="787d7-117">Il comando aggiunge l'interfaccia `IFinances` del componente `ItemOrders.IFinancial` dell'applicazione COM+ OnlineStore al set di interfacce da esporre come servizi Web.</span><span class="sxs-lookup"><span data-stu-id="787d7-117">The command adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="787d7-118">Il servizio utilizza la modalità di hosting COM+ e pertanto richiede l’attivazione esplicita dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="787d7-118">The service uses the COM+ hosting mode and therefore requires explicit application activation.</span></span>  
  
     <span data-ttu-id="787d7-119">Sebbene sia possibile utilizzare il carattere jolly asterisco ( \* ) per il componente e l'interfaccia, evitare di utilizzarlo perché potrebbe essere necessario esporre solo le funzionalità selezionate come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="787d7-119">While the wildcard asterisk (\*) character can be used for the component and the interface, avoid using it because you might want to expose only selected functionality as a Web service.</span></span> <span data-ttu-id="787d7-120">Se si esegue l'applicazione con una versione successiva di questo componente, l'utilizzo del carattere jolly può comportare l'esposizione indesiderata delle interfacce non presenti al momento della determinazione della sintassi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="787d7-120">If run with a future version of this component, using the wildcard may unintentionally expose interfaces that may not have been present when the configuration syntax was determined.</span></span>  
  
     <span data-ttu-id="787d7-121">L'opzione /verbose consente di visualizzare sia gli avvisi sia gli errori.</span><span class="sxs-lookup"><span data-stu-id="787d7-121">The /verbose option instructs the tool to display warnings in addition to any errors.</span></span>  
  
     <span data-ttu-id="787d7-122">Il contratto del servizio esposto contiene tutti i metodi dell'interfaccia `IFinances`.</span><span class="sxs-lookup"><span data-stu-id="787d7-122">The contract for the exposed service will contain all of the methods from the `IFinances` interface.</span></span>  
  
## <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="787d7-123">Per aggiungere solo metodi specifici da un'interfaccia al set di interfacce esposte come servizi Web, usando la modalità di hosting COM+</span><span class="sxs-lookup"><span data-stu-id="787d7-123">To add only specific methods from an interface to the set of interfaces exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="787d7-124">Eseguire ComSvcConfig utilizzando le opzioni `/install` e `/hosting:complus` denominando in modo esplicito i metodi da aggiungere, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-124">Run ComSvcConfig using the `/install` and `/hosting:complus` options with explicit naming of the required methods, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="787d7-125">Il comando aggiunge come operazioni al contratto del servizio esposto solo i metodi `Credit` e `Debit` dell'interfaccia `IFinances`.</span><span class="sxs-lookup"><span data-stu-id="787d7-125">The command adds only the `Credit` and `Debit` methods from the `IFinances` interface as operations to the exposed service contract.</span></span> <span data-ttu-id="787d7-126">Tutti gli altri metodi dell'interfaccia vengono omessi dal contratto e non sono chiamabili dai client del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="787d7-126">All other methods on the interface will be omitted from the contract and will not be callable from Web service clients.</span></span>  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-web-hosting-mode"></a><span data-ttu-id="787d7-127">Per aggiungere un'interfaccia al set di interfacce esposte come servizi Web mediante la modalità di hosting Web</span><span class="sxs-lookup"><span data-stu-id="787d7-127">To add an interface to the set of interfaces exposed as Web services, using the Web hosting mode</span></span>  
  
- <span data-ttu-id="787d7-128">Eseguire ComSvcConfig utilizzando le opzioni `/install` e `/hosting:was`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-128">Run ComSvcConfig using the `/install` option and the `/hosting:was` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     <span data-ttu-id="787d7-129">Questo comando aggiunge l'interfaccia `IStockLevels` del componente `ItemInventory.Warehouse` dell'applicazione COM+ OnlineWarehouse al set di interfacce da esporre come servizi Web.</span><span class="sxs-lookup"><span data-stu-id="787d7-129">The command adds the `IStockLevels` interface on the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="787d7-130">Il servizio è ospitato su Web nella directory virtuale dell'applicazione OnlineWarehouse di IIS anziché in COM+. L'applicazione viene pertanto attivata automaticamente secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="787d7-130">The service is Web hosted in the OnlineWarehouse virtual directory of IIS rather than in COM+, and thus the application is automatically activated as required.</span></span>  
  
     <span data-ttu-id="787d7-131">Per utilizzare la configurazione host Web in corso occorre utilizzare la console di amministrazione di Component Services allo scopo di configurare l'applicazione COM+ affinché funzioni come applicazione libreria anziché come applicazione server.</span><span class="sxs-lookup"><span data-stu-id="787d7-131">To use the Web-hosted in-process configuration, the COM+ application must be configured to run as a Library application rather than a Server application using the Component Services administration console.</span></span> <span data-ttu-id="787d7-132">Le applicazioni configurate come applicazioni server utilizzano la modalità host Web standard e prevedono un hop di processo per elaborare ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="787d7-132">Applications configured as Server applications use the standard Web-hosted mode and incur a process hop to process each request.</span></span>  
  
     <span data-ttu-id="787d7-133">L'opzione `/mex` aggiunge un endpoint di servizio di scambio metadati (MEX, Metadata Exchange) che utilizza lo stesso trasporto utilizzato dall'endpoint di servizio dell'applicazione per supportare i client che desiderano recuperare una definizione di contratto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="787d7-133">The `/mex` option adds an additional Metadata Exchange (MEX) service endpoint that uses the same transport as the application's service endpoint to support clients that want to retrieve a contract definition from the service.</span></span>  
  
## <a name="to-remove-a-web-service-for-a-specified-interface"></a><span data-ttu-id="787d7-134">Per rimuovere un servizio Web di un'interfaccia specificata</span><span class="sxs-lookup"><span data-stu-id="787d7-134">To remove a Web service for a specified interface</span></span>  
  
- <span data-ttu-id="787d7-135">Eseguire ComSvcConfig utilizzando l'opzione `/uninstall`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-135">Run ComSvcConfig using the `/uninstall` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     <span data-ttu-id="787d7-136">Il comando rimuove l'interfaccia `IFinances` del componente `ItemOrders.Financial` dell'applicazione COM+ OnlineStore.</span><span class="sxs-lookup"><span data-stu-id="787d7-136">The command removes the `IFinances` interface on the `ItemOrders.Financial` component (from the OnlineStore COM+ application).</span></span>  
  
## <a name="to-list-currently-exposed-interfaces"></a><span data-ttu-id="787d7-137">Per elencare le interfacce attualmente esposte</span><span class="sxs-lookup"><span data-stu-id="787d7-137">To list currently exposed interfaces</span></span>  
  
- <span data-ttu-id="787d7-138">Eseguire ComSvcConfig utilizzando l'opzione `/list`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-138">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /list  
    ```  
  
     <span data-ttu-id="787d7-139">Il comando elenca le interfacce attualmente esposte nell'ambito del computer locale, insieme all'indirizzo e ai dettagli di associazione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="787d7-139">The command lists the currently exposed interfaces, along with the corresponding address and binding details, scoped to the local machine.</span></span>  
  
## <a name="to-list-specific-currently-exposed-interfaces"></a><span data-ttu-id="787d7-140">Per elencare determinate interfacce attualmente esposte</span><span class="sxs-lookup"><span data-stu-id="787d7-140">To list specific currently exposed interfaces</span></span>  
  
- <span data-ttu-id="787d7-141">Eseguire ComSvcConfig utilizzando l'opzione `/list`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-141">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     <span data-ttu-id="787d7-142">Il comando elenca le interfacce ospitate in COM+ attualmente esposte, insieme all'indirizzo e ai dettagli di associazione corrispondenti, relative all'applicazione COM+ OnlineStore contenuta nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="787d7-142">The command lists currently exposed COM+-hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
## <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a><span data-ttu-id="787d7-143">Per visualizzare la Guida relativa alle opzioni disponibili nell'utilità</span><span class="sxs-lookup"><span data-stu-id="787d7-143">To display help on the options that can be used with the utility</span></span>  
  
- <span data-ttu-id="787d7-144">Eseguire ComSvcConfig utilizzando l'opzione /?</span><span class="sxs-lookup"><span data-stu-id="787d7-144">Run ComSvcConfig using the /?</span></span> <span data-ttu-id="787d7-145">come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="787d7-145">option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="787d7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787d7-146">See also</span></span>

- [<span data-ttu-id="787d7-147">Panoramica sull'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="787d7-147">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
