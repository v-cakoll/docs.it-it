---
title: Utilizzo degli strumenti di sviluppo WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e315c9e77eace9bdb0e66abed203452e5d7f9bb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="7bec0-102">Utilizzo degli strumenti di sviluppo WCF</span><span class="sxs-lookup"><span data-stu-id="7bec0-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="7bec0-103">In questa sezione vengono descritti gli strumenti di sviluppo di Visual Studio che possono fornire assistenza nello sviluppo di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]servizio.</span><span class="sxs-lookup"><span data-stu-id="7bec0-103">This section describes the Visual Studio development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="7bec0-104">È possibile utilizzare i modelli di Visual Studio come base per rapidamente il proprio servizio di compilazione, quindi utilizzare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automatico servizio e [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test per eseguire il debug e testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="7bec0-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="7bec0-105">Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="7bec0-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="7bec0-106">Strumenti dello sviluppatore WCF</span><span class="sxs-lookup"><span data-stu-id="7bec0-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="7bec0-107">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="7bec0-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="7bec0-108">È possibile utilizzare i modelli di progetto e di elemento Visual Studio predefiniti in Visual Studio per compilare rapidamente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizi e le relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7bec0-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="7bec0-109">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7bec0-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="7bec0-110">Il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automatico servizio (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio è stato implementato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7bec0-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="7bec0-111">È quindi possibile testare il servizio mediante Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) o un client specifico per trovare e correggere qualsiasi errore potenziale.</span><span class="sxs-lookup"><span data-stu-id="7bec0-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="7bec0-112">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7bec0-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="7bec0-113">Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="7bec0-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="7bec0-114">In combinazione con Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], offre una funzione di test del servizio trasparente.</span><span class="sxs-lookup"><span data-stu-id="7bec0-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="7bec0-115">Generazione di classi di tipi dati da XML</span><span class="sxs-lookup"><span data-stu-id="7bec0-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="7bec0-116">I dati XML archiviati negli Appunti possono essere incollati in una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="7bec0-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="7bec0-117">Le classi definite nei dati verranno convertite in tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="7bec0-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="7bec0-118">Utilizzo degli strumenti senza privilegio di amministratore</span><span class="sxs-lookup"><span data-stu-id="7bec0-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="7bec0-119">Per consentire agli utenti senza privilegio di amministratore di sviluppare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7bec0-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="7bec0-120">L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer.</span><span class="sxs-lookup"><span data-stu-id="7bec0-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="7bec0-121">Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7bec0-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="7bec0-122">Consente inoltre agli utenti di utilizzare Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) senza che vengano concessi privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7bec0-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="7bec0-123">È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="7bec0-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="7bec0-124">Di seguito è riportato un esempio di utilizzo di Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="7bec0-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7bec0-125"> Netsh.exe, vedere [come utilizzare lo strumento di Netsh.exe e opzioni della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="7bec0-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bec0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bec0-126">See Also</span></span>  
 [<span data-ttu-id="7bec0-127">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="7bec0-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="7bec0-128">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7bec0-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="7bec0-129">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7bec0-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
