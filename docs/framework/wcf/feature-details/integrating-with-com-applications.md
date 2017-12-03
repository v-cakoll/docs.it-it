---
title: Integrazione con applicazioni COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfe452b41c39598e237633490d09cd267fda04ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="85445-102">Integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="85445-102">Integrating with COM Applications</span></span>
<span data-ttu-id="85445-103">I servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono essere integrati direttamente nel codice esistente usando il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85445-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="85445-104">Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="85445-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85445-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="85445-105">In This Section</span></span>  
 [<span data-ttu-id="85445-106">L'integrazione con panoramica delle applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="85445-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="85445-107">Fornisce una panoramica delle parti principali del processo di integrazione.</span><span class="sxs-lookup"><span data-stu-id="85445-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="85445-108">Procedura: registrare e configurare un Moniker di servizio</span><span class="sxs-lookup"><span data-stu-id="85445-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="85445-109">Per usare il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="85445-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="85445-110">Procedura: usare il Moniker del servizio Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="85445-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="85445-111">Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="85445-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="85445-112">Procedura: usare un Moniker servizio con i contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="85445-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="85445-113">Descrive come chiamare un esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando un moniker WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85445-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="85445-114">Procedura: usare un Moniker servizio con contratti di scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="85445-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="85445-115">Descrive come chiamare un esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che specifica un endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="85445-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="85445-116">Procedura: specificare le credenziali di sicurezza del canale</span><span class="sxs-lookup"><span data-stu-id="85445-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="85445-117">Il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta l'interfaccia `IChannelCredentials` che consente un intervallo di metodi alternativi per la specifica di credenziali del canale.</span><span class="sxs-lookup"><span data-stu-id="85445-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="85445-118">Riferimento</span><span class="sxs-lookup"><span data-stu-id="85445-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="85445-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85445-119">See Also</span></span>  
 [<span data-ttu-id="85445-120">L'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="85445-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
