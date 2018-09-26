---
title: Integrazione AJAX e supporto JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: bcf1cab9386d9d9503af6258c1bb39f8744c073b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47210188"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="186bf-102">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="186bf-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="186bf-103">Il supporto di Windows Communication Foundation (WCF) per ASP.NET Asynchronous JavaScript and XML (AJAX) e il formato di dati JavaScript Object Notation (JSON) consentire ai servizi WCF di esporre operazioni ai client AJAX.</span><span class="sxs-lookup"><span data-stu-id="186bf-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="186bf-104">I client AJAX sono pagine Web che eseguono codice JavaScript e l'accesso a questi servizi WCF tramite richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="186bf-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="186bf-105">Negli argomenti di questa sezione vengono fornite informazioni su questo supporto e su come implementarlo.</span><span class="sxs-lookup"><span data-stu-id="186bf-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="186bf-106">Per altre informazioni su ASP.NET AJAX e all'integrazione con ASP.NET 2.0, vedere [Panoramica di ASP.NET AJAX](https://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="186bf-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="186bf-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="186bf-107">In This Section</span></span>  
 [<span data-ttu-id="186bf-108">Creazione di servizi WCF per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="186bf-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="186bf-109">Viene descritto come un servizio WCF può essere esposto ai client AJAX mediante l'aggiunta dell'endpoint AJAX appropriato tramite configurazione o utilizzando una factory dell'host del servizio personalizzata per generare un host del servizio che configura automaticamente l'endpoint AJAX.</span><span class="sxs-lookup"><span data-stu-id="186bf-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="186bf-110">Creazione di servizi WCF AJAX senza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="186bf-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="186bf-111">Viene descritto come creare un servizio WCF senza utilizzare ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="186bf-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="186bf-112">Supporto per JSON e altri formati di trasferimento dati</span><span class="sxs-lookup"><span data-stu-id="186bf-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="186bf-113">Descrive il supporto del formato JSON utilizzato in genere al posto di XML per la messaggistica con i servizi ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="186bf-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="186bf-114">Procedura: Eseguire la migrazione di servizi Web ASP.NET abilitati AJAX in WCF</span><span class="sxs-lookup"><span data-stu-id="186bf-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="186bf-115">Viene descritto come eseguire la migrazione di un servizio Web ASP.NET per AJAX a un servizio Web WCF.</span><span class="sxs-lookup"><span data-stu-id="186bf-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186bf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="186bf-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="186bf-117">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="186bf-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
