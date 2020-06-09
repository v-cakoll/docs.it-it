---
title: Integrazione AJAX e supporto JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 3054c3c6faa8dfe621c706d8df031c23d497da0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576512"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="d46e1-102">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="d46e1-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="d46e1-103">Il supporto Windows Communication Foundation (WCF) per ASP.NET Asynchronous JavaScript and XML (AJAX) e il formato dati JavaScript Object Notation (JSON) consentono ai servizi WCF di esporre le operazioni ai client AJAX.</span><span class="sxs-lookup"><span data-stu-id="d46e1-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="d46e1-104">I client AJAX sono pagine Web che eseguono codice JavaScript e accedono a questi servizi WCF tramite richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="d46e1-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="d46e1-105">Negli argomenti di questa sezione vengono fornite informazioni su questo supporto e su come implementarlo.</span><span class="sxs-lookup"><span data-stu-id="d46e1-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="d46e1-106">Per altre informazioni su ASP.NET AJAX e la relativa integrazione con ASP.NET 2,0, vedere [Panoramica di ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d46e1-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d46e1-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d46e1-107">In This Section</span></span>  
 [<span data-ttu-id="d46e1-108">Creazione di servizi WCF per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="d46e1-108">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="d46e1-109">Viene descritto il modo in cui un servizio WCF può essere esposto ai client AJAX aggiungendo l'endpoint AJAX appropriato tramite la configurazione o utilizzando una factory host del servizio personalizzata per generare un host del servizio che configura automaticamente l'endpoint AJAX.</span><span class="sxs-lookup"><span data-stu-id="d46e1-109">Describes how a WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="d46e1-110">Creazione di servizi WCF AJAX senza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d46e1-110">Creating WCF AJAX Services without ASP.NET</span></span>](creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="d46e1-111">Viene descritto come creare un servizio WCF senza usare ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d46e1-111">Describes how to create a WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="d46e1-112">Supporto per JSON e altri formati di trasferimento dati</span><span class="sxs-lookup"><span data-stu-id="d46e1-112">Support for JSON and Other Data Transfer Formats</span></span>](support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="d46e1-113">Descrive il supporto del formato JSON utilizzato in genere al posto di XML per la messaggistica con i servizi ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="d46e1-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="d46e1-114">Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF</span><span class="sxs-lookup"><span data-stu-id="d46e1-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="d46e1-115">Viene descritto come eseguire la migrazione di un servizio Web ASP.NET abilitato per AJAX a un servizio Web WCF.</span><span class="sxs-lookup"><span data-stu-id="d46e1-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46e1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d46e1-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="d46e1-117">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="d46e1-117">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
