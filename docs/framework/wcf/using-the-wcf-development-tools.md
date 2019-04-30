---
title: Utilizzo degli strumenti di sviluppo WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 1ffa3be4a6b8976ab978ea995e8b2c1faaacf0ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051715"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="b0fc9-102">Utilizzo degli strumenti di sviluppo WCF</span><span class="sxs-lookup"><span data-stu-id="b0fc9-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="b0fc9-103">In questa sezione vengono descritti gli strumenti di sviluppo di Visual Studio che possono facilitare lo sviluppo del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="b0fc9-104">È possibile usare i modelli di Visual Studio come base per compilare rapidamente un servizio personalizzato, quindi utilizzare Host automatico servizio di WCF e Client di prova WCF per eseguire il debug e testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="b0fc9-105">Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="b0fc9-106">Strumenti dello sviluppatore WCF</span><span class="sxs-lookup"><span data-stu-id="b0fc9-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="b0fc9-107">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="b0fc9-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="b0fc9-108">È possibile usare i modelli predefiniti di progetti ed elementi di Visual Studio in Visual Studio per compilare rapidamente i servizi WCF e le relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="b0fc9-109">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="b0fc9-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="b0fc9-110">L'Host automatico servizio di WCF (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio che è stato implementato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-110">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="b0fc9-111">È quindi possibile testare il servizio utilizzando il Client di prova WCF (wcfTestClient.exe) o il proprio client di individuare e correggere qualsiasi errore potenziale.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-111">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="b0fc9-112">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="b0fc9-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="b0fc9-113">Client di prova WCF (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare che la risposta del servizio invia di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-113">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="b0fc9-114">Fornisce un servizio facile test combinazione con Host automatico servizio di WCF.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-114">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="b0fc9-115">Generazione di classi di tipi dati da XML</span><span class="sxs-lookup"><span data-stu-id="b0fc9-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="b0fc9-116">I dati XML archiviati negli Appunti possono essere incollati in una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="b0fc9-117">Le classi definite nei dati verranno convertite in tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="b0fc9-118">Utilizzo degli strumenti senza privilegio di amministratore</span><span class="sxs-lookup"><span data-stu-id="b0fc9-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="b0fc9-119">Per abilitare gli utenti senza privilegi di amministratore per lo sviluppo di servizi WCF, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-119">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="b0fc9-120">L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="b0fc9-121">Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="b0fc9-122">Consente inoltre agli utenti di utilizzare Host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-122">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="b0fc9-123">È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="b0fc9-124">Di seguito è riportato un esempio di utilizzo di Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="b0fc9-125">Per altre informazioni sulle Netsh.exe, vedere [come usare lo strumento di Netsh.exe e opzioni della riga di comando](https://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="b0fc9-125">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fc9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0fc9-126">See also</span></span>

- [<span data-ttu-id="b0fc9-127">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="b0fc9-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)
- [<span data-ttu-id="b0fc9-128">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="b0fc9-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="b0fc9-129">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="b0fc9-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
