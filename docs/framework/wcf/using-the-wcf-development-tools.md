---
title: Utilizzo degli strumenti di sviluppo WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d253f38fab21496dd305cc67e7b6e84846579f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="9a0a9-102">Utilizzo degli strumenti di sviluppo WCF</span><span class="sxs-lookup"><span data-stu-id="9a0a9-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="9a0a9-103">Questa sezione viene descritto il [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] gli strumenti di sviluppo che possono fornire assistenza nello sviluppo del [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="9a0a9-104">È possibile utilizzare il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] modelli come base per compilare rapidamente il proprio servizio, quindi utilizzare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automatico servizio e [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test per eseguire il debug e testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="9a0a9-105">Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="9a0a9-106">Strumenti dello sviluppatore WCF</span><span class="sxs-lookup"><span data-stu-id="9a0a9-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="9a0a9-107">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="9a0a9-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="9a0a9-108">È possibile utilizzare predefiniti [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] modelli di progetto e di elemento in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per compilare rapidamente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizi e le relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="9a0a9-109">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9a0a9-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="9a0a9-110">Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfSvcHost.exe) consente di avviare il debugger (F5) di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per attivare automaticamente funzioni di host e test di un servizio implementato.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="9a0a9-111">È quindi possibile testare il servizio mediante Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) o un client specifico per trovare e correggere qualsiasi errore potenziale.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="9a0a9-112">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9a0a9-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="9a0a9-113">Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="9a0a9-114">In combinazione con Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], offre una funzione di test del servizio trasparente.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="9a0a9-115">Generazione di classi di tipi dati da XML</span><span class="sxs-lookup"><span data-stu-id="9a0a9-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="9a0a9-116">I dati XML archiviati negli Appunti possono essere incollati in una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="9a0a9-117">Le classi definite nei dati verranno convertite in tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="9a0a9-118">Utilizzo degli strumenti senza privilegio di amministratore</span><span class="sxs-lookup"><span data-stu-id="9a0a9-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="9a0a9-119">Per consentire agli utenti senza privilegio di amministratore di sviluppare servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], viene creato un ACL (Elenco di controllo di accesso) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a0a9-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="9a0a9-120">L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="9a0a9-121">Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="9a0a9-122">Consente inoltre agli utenti di utilizzare Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) senza che vengano concessi privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="9a0a9-123">È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="9a0a9-124">Di seguito è riportato un esempio di utilizzo di Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="9a0a9-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9a0a9-125">Netsh.exe, vedere [sull'utilizzo dello strumento Netsh.exe e parametri della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="9a0a9-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0a9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a0a9-126">See Also</span></span>  
 [<span data-ttu-id="9a0a9-127">Modelli di Visual Studio WCF</span><span class="sxs-lookup"><span data-stu-id="9a0a9-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="9a0a9-128">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9a0a9-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="9a0a9-129">Client di prova WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9a0a9-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
