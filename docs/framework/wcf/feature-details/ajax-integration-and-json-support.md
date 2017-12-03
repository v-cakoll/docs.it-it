---
title: Integrazione AJAX e supporto JSON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98efc62a133b86ab71e34671bc6385a5a94897ea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="e28f6-102">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="e28f6-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="e28f6-103">Il supporto [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per ASP.NET AJAX (Asynchronous JavaScript and XML) e il formato dati JSON (JavaScript Object Notation) consentono ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di esporre operazioni ai client AJAX.</span><span class="sxs-lookup"><span data-stu-id="e28f6-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="e28f6-104">I client AJAX sono pagine Web che eseguono codice JavaScript e accedono a questi servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizzando richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="e28f6-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="e28f6-105">Negli argomenti di questa sezione vengono fornite informazioni su questo supporto e su come implementarlo.</span><span class="sxs-lookup"><span data-stu-id="e28f6-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e28f6-106">ASP.NET AJAX e l'integrazione con ASP.NET 2.0, vedere [Panoramica di ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="e28f6-106"> ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e28f6-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e28f6-107">In This Section</span></span>  
 [<span data-ttu-id="e28f6-108">Creazione di servizi WCF per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="e28f6-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="e28f6-109">Viene descritto come è possibile esporre un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a client AJAX mediante l'aggiunta dell'endpoint AJAX appropriato tramite la configurazione o una factory di host del servizio personalizzata per generare un host del servizio che configuri automaticamente l'endpoint AJAX.</span><span class="sxs-lookup"><span data-stu-id="e28f6-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="e28f6-110">Creazione di servizi WCF AJAX senza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e28f6-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="e28f6-111">Descrive come creare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senza utilizzare ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e28f6-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="e28f6-112">Supporto per JSON e altri dati formati di trasferimento</span><span class="sxs-lookup"><span data-stu-id="e28f6-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="e28f6-113">Descrive il supporto del formato JSON utilizzato in genere al posto di XML per la messaggistica con i servizi ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="e28f6-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="e28f6-114">Procedura: eseguire la migrazione di servizi Web di ASP.NET con supporto AJAX a WCF</span><span class="sxs-lookup"><span data-stu-id="e28f6-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="e28f6-115">Descrive come eseguire la migrazione di un servizio Web ASP.NET con supporto AJAX a un servizio Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e28f6-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28f6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e28f6-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="e28f6-117">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="e28f6-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
