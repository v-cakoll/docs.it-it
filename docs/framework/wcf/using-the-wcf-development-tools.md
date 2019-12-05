---
title: Uso degli strumenti di sviluppo WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 59913f4c00c32699d788e2a0244798fc652361be
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802410"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="7e913-102">Uso degli strumenti di sviluppo WCF</span><span class="sxs-lookup"><span data-stu-id="7e913-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="7e913-103">Questa sezione descrive gli strumenti di sviluppo di Visual Studio che possono risultare utili per lo sviluppo di WCFservice.</span><span class="sxs-lookup"><span data-stu-id="7e913-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="7e913-104">È possibile utilizzare i modelli di Visual Studio come base per creare rapidamente un servizio personalizzato, quindi utilizzare l'host automatico del servizio WCF e il client di prova WCF per eseguire il debug e il test del servizio.</span><span class="sxs-lookup"><span data-stu-id="7e913-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="7e913-105">Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="7e913-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
 
 > [!NOTE]
 > <span data-ttu-id="7e913-106">A partire da Visual Studio 2017, gli strumenti di sviluppo WCF non sono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7e913-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="7e913-107">Per usare queste funzionalità, è necessario assicurarsi che il componente Windows Communication Foundation sia selezionato nel programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e913-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="7e913-108">Strumenti dello sviluppatore WCF</span><span class="sxs-lookup"><span data-stu-id="7e913-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="7e913-109">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="7e913-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="7e913-110">È possibile utilizzare i modelli di progetto e di elemento predefiniti di Visual Studio in Visual Studio per compilare rapidamente i servizi WCF e le applicazioni circostanti.</span><span class="sxs-lookup"><span data-stu-id="7e913-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="7e913-111">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7e913-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="7e913-112">L'host automatico del servizio WCF (WcfSvcHost. exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare automaticamente un servizio implementato.</span><span class="sxs-lookup"><span data-stu-id="7e913-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="7e913-113">È quindi possibile testare il servizio utilizzando il client di prova WCF (wcfTestClient. exe) o il client per individuare e correggere eventuali errori potenziali.</span><span class="sxs-lookup"><span data-stu-id="7e913-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="7e913-114">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7e913-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="7e913-115">Il client di prova WCF (WcfTestClient. exe) è uno strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="7e913-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="7e913-116">Offre un'esperienza di test dei servizi senza problemi in combinazione con l'host automatico del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="7e913-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="7e913-117">Generazione di classi di tipi dati da XML</span><span class="sxs-lookup"><span data-stu-id="7e913-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="7e913-118">I dati XML archiviati negli Appunti possono essere incollati in una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="7e913-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="7e913-119">Le classi definite nei dati verranno convertite in tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="7e913-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="7e913-120">Utilizzo degli strumenti senza privilegio di amministratore</span><span class="sxs-lookup"><span data-stu-id="7e913-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="7e913-121">Per consentire agli utenti senza privilegi di amministratore di sviluppare servizi WCF, viene creato un ACL (elenco di controllo di accesso) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e913-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="7e913-122">L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer.</span><span class="sxs-lookup"><span data-stu-id="7e913-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="7e913-123">Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7e913-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="7e913-124">Consente inoltre agli utenti di utilizzare l'host automatico del servizio WCF (wcfSvcHost. exe) senza concedere loro privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7e913-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="7e913-125">È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="7e913-125">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="7e913-126">Di seguito è riportato un esempio di utilizzo di Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="7e913-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="7e913-127">Per ulteriori informazioni su Netsh. exe, vedere [come utilizzare lo strumento Netsh. exe e le opzioni della riga di comando](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="7e913-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e913-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e913-128">See also</span></span>

- [<span data-ttu-id="7e913-129">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="7e913-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="7e913-130">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7e913-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="7e913-131">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7e913-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
