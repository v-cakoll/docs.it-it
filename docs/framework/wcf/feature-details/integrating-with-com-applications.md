---
title: Integrazione con applicazioni COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: dc3bbe0ee72ca5583b1e52a61c914ad866a22a05
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596810"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="bd200-102">Integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="bd200-102">Integrating with COM Applications</span></span>
<span data-ttu-id="bd200-103">I servizi Windows Communication Foundation (WCF) possono essere integrati direttamente nel codice esistente usando il moniker del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="bd200-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="bd200-104">Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="bd200-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd200-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bd200-105">In This Section</span></span>  
 [<span data-ttu-id="bd200-106">Panoramica dell'integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="bd200-106">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)  
 <span data-ttu-id="bd200-107">Fornisce una panoramica delle parti principali del processo di integrazione.</span><span class="sxs-lookup"><span data-stu-id="bd200-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="bd200-108">Procedura: registrare e configurare un moniker servizio</span><span class="sxs-lookup"><span data-stu-id="bd200-108">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="bd200-109">Per utilizzare il moniker del servizio WCF all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="bd200-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="bd200-110">Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="bd200-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="bd200-111">Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="bd200-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="bd200-112">Procedura: usare un moniker di servizio con i contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="bd200-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="bd200-113">Viene descritto come chiamare un esempio WCF utilizzando un moniker WSDL WCF.</span><span class="sxs-lookup"><span data-stu-id="bd200-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="bd200-114">Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="bd200-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="bd200-115">Viene descritto come chiamare un esempio WCF utilizzando un moniker WCF che specifica un endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="bd200-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="bd200-116">Procedura: specificare credenziali di sicurezza del canale</span><span class="sxs-lookup"><span data-stu-id="bd200-116">How to: Specify Channel Security Credentials</span></span>](how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="bd200-117">Il moniker del servizio WCF supporta l' `IChannelCredentials` interfaccia che consente un intervallo di metodi alternativi per specificare le credenziali del canale.</span><span class="sxs-lookup"><span data-stu-id="bd200-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bd200-118">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="bd200-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="bd200-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd200-119">See also</span></span>

- [<span data-ttu-id="bd200-120">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="bd200-120">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
