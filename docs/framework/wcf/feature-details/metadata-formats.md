---
title: Formati dei metadati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7812023fbe2159daba205727e20e1b69b84686
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-formats"></a><span data-ttu-id="6bcbb-102">Formati dei metadati</span><span class="sxs-lookup"><span data-stu-id="6bcbb-102">Metadata Formats</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="6bcbb-103"> supporta i formati di metadati riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-103"> supports the metadata formats in the following table.</span></span>  
  
## <a name="metadata-specifications-and-usage"></a><span data-ttu-id="6bcbb-104">Specifiche e utilizzo dei metadati</span><span class="sxs-lookup"><span data-stu-id="6bcbb-104">Metadata Specifications and Usage</span></span>  
  
|<span data-ttu-id="6bcbb-105">Protocollo</span><span class="sxs-lookup"><span data-stu-id="6bcbb-105">Protocol</span></span>|<span data-ttu-id="6bcbb-106">Specifica e utilizzo</span><span class="sxs-lookup"><span data-stu-id="6bcbb-106">Specification and usage</span></span>|  
|--------------|-----------------------------|  
|<span data-ttu-id="6bcbb-107">WSDL 1.1</span><span class="sxs-lookup"><span data-stu-id="6bcbb-107">WSDL 1.1</span></span>|[<span data-ttu-id="6bcbb-108">Web Services Description Language (WSDL) 1.1</span><span class="sxs-lookup"><span data-stu-id="6bcbb-108">Web Services Description Language (WSDL) 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-109"> usa Web Services Description Language (WSDL) per descrivere i servizi.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-109"> uses Web Services Description Language (WSDL) to describe services.</span></span>|  
|<span data-ttu-id="6bcbb-110">XML Schema</span><span class="sxs-lookup"><span data-stu-id="6bcbb-110">XML Schema</span></span>|<span data-ttu-id="6bcbb-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) e [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span><span class="sxs-lookup"><span data-stu-id="6bcbb-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span></span><br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-112"> usa l'XML Schema per descrivere tipi di dati usati nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-112"> uses the XML Schema to describe data types used in messages.</span></span>|  
|<span data-ttu-id="6bcbb-113">WS Policy</span><span class="sxs-lookup"><span data-stu-id="6bcbb-113">WS Policy</span></span>|[<span data-ttu-id="6bcbb-114">Criteri di servizi Web 1.2 - Framework (WS-Policy)</span><span class="sxs-lookup"><span data-stu-id="6bcbb-114">Web Services Policy 1.2 - Framework (WS-Policy)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [<span data-ttu-id="6bcbb-115">Criteri di servizi Web 1.5 - Framework</span><span class="sxs-lookup"><span data-stu-id="6bcbb-115">Web Services Policy 1.5 - Framework</span></span>](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-116"> usa la specifica WS-Policy 1.2 o 1.5 insieme ad asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-116"> uses the WS-Policy 1.2 or 1.5 specifications with domain-specific assertions to describe service requirements and capabilities.</span></span>|  
|<span data-ttu-id="6bcbb-117">WS Policy Attachments</span><span class="sxs-lookup"><span data-stu-id="6bcbb-117">WS Policy Attachments</span></span>|[<span data-ttu-id="6bcbb-118">Criteri di servizi Web 1.2 - allegato (WS-PolicyAttachment)</span><span class="sxs-lookup"><span data-stu-id="6bcbb-118">Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-119"> implementa WS-PolicyAttachments per allegare espressioni di criteri a vari ambiti in WSDL.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-119"> implements WS-Policy Attachments to attach policy expressions at various scopes in WSDL.</span></span>|  
|<span data-ttu-id="6bcbb-120">WS Metadata Exchange</span><span class="sxs-lookup"><span data-stu-id="6bcbb-120">WS Metadata Exchange</span></span>|[<span data-ttu-id="6bcbb-121">Web Services Metadata Exchange (WS-MetadataExchange) versione 1.1</span><span class="sxs-lookup"><span data-stu-id="6bcbb-121">Web Services Metadata Exchange (WS-MetadataExchange) version 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-122"> implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-122"> implements WS-MetadataExchange to retrieve XML Schema, WSDL, and WS-Policy.</span></span>|  
|<span data-ttu-id="6bcbb-123">WS Addressing Binding per WSDL</span><span class="sxs-lookup"><span data-stu-id="6bcbb-123">WS Addressing Binding for WSDL</span></span>|[<span data-ttu-id="6bcbb-124">Web Services Addressing 1.0 con associazione WSDL</span><span class="sxs-lookup"><span data-stu-id="6bcbb-124">Web Services Addressing 1.0 - WSDL Binding</span></span>](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6bcbb-125"> implementa WS-Addressing Binding per WSDL per collegare informazioni di indirizzamento in WSDL.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-125"> implements WS-Addressing Binding for WSDL to attach addressing information in WSDL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bcbb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bcbb-126">See Also</span></span>  
 [<span data-ttu-id="6bcbb-127">Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6bcbb-127">Web Services Protocols Supported by System-Provided Interoperability Bindings</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [<span data-ttu-id="6bcbb-128">WSDL e criteri</span><span class="sxs-lookup"><span data-stu-id="6bcbb-128">WSDL and Policy</span></span>](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
