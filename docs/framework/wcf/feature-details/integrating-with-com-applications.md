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
ms.openlocfilehash: 8fa802ce20bfde3579258a5d34bc5d7f68aaaea3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657402"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="0b726-102">Integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="0b726-102">Integrating with COM Applications</span></span>
<span data-ttu-id="0b726-103">Servizi Windows Communication Foundation (WCF) possono essere integrati direttamente nel codice esistente usando il moniker del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="0b726-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="0b726-104">Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="0b726-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b726-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0b726-105">In This Section</span></span>  
 [<span data-ttu-id="0b726-106">Panoramica dell'integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="0b726-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="0b726-107">Fornisce una panoramica delle parti principali del processo di integrazione.</span><span class="sxs-lookup"><span data-stu-id="0b726-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="0b726-108">Procedura: Registrare e configurare un Moniker servizio</span><span class="sxs-lookup"><span data-stu-id="0b726-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="0b726-109">Per usare il moniker del servizio WCF all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="0b726-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="0b726-110">Procedura: Usare il Moniker del servizio Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="0b726-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="0b726-111">Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="0b726-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="0b726-112">Procedura: Usare un Moniker servizio con contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="0b726-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="0b726-113">Viene descritto come chiamare un esempio WCF usando un moniker WSDL WCF.</span><span class="sxs-lookup"><span data-stu-id="0b726-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="0b726-114">Procedura: Usare un Moniker servizio con contratti per lo scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="0b726-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="0b726-115">Viene descritto come chiamare un esempio WCF usando un moniker WCF che specifica un endpoint Mex.</span><span class="sxs-lookup"><span data-stu-id="0b726-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="0b726-116">Procedura: Specificare le credenziali di sicurezza del canale</span><span class="sxs-lookup"><span data-stu-id="0b726-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="0b726-117">Il moniker del servizio WCF supporta i `IChannelCredentials` interfaccia che consente un intervallo di metodi alternativi per specificare le credenziali del canale.</span><span class="sxs-lookup"><span data-stu-id="0b726-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0b726-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0b726-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="0b726-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b726-119">See also</span></span>
- [<span data-ttu-id="0b726-120">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="0b726-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
