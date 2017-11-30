---
title: Trasferimento dati e serializzazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41357c9a039414ac692bac69337b2963d5c6b341
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="a84c9-102">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="a84c9-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="a84c9-103">In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati.</span><span class="sxs-lookup"><span data-stu-id="a84c9-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="a84c9-104">Gli sviluppatori di un servizio o di un client devono comprendere inoltre come [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] gestisce i dati e la serializzazione dei dati per creare applicazioni efficienti e facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="a84c9-104">As a developer of a service or client, you must also understand how [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a84c9-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a84c9-105">In This Section</span></span>  
 [<span data-ttu-id="a84c9-106">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="a84c9-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="a84c9-107">Descrive i concetti di base del trasferimento dati nei servizi.</span><span class="sxs-lookup"><span data-stu-id="a84c9-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="a84c9-108">Uso di contratti dati</span><span class="sxs-lookup"><span data-stu-id="a84c9-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="a84c9-109">Descrive i contratti dati, come crearli e utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="a84c9-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="a84c9-110">Serializzatore dei contratti dati</span><span class="sxs-lookup"><span data-stu-id="a84c9-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="a84c9-111">Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a84c9-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="a84c9-112">Utilizzo della classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="a84c9-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="a84c9-113">Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a84c9-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="a84c9-114">Utilizzo dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="a84c9-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="a84c9-115">Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="a84c9-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="a84c9-116">Utilizzo della classe Message</span><span class="sxs-lookup"><span data-stu-id="a84c9-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="a84c9-117">Descrive come utilizzare le funzionalità di una classe Message.</span><span class="sxs-lookup"><span data-stu-id="a84c9-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="a84c9-118">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="a84c9-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="a84c9-119">Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.</span><span class="sxs-lookup"><span data-stu-id="a84c9-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="a84c9-120">Dati di grandi dimensioni e il flusso</span><span class="sxs-lookup"><span data-stu-id="a84c9-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="a84c9-121">Descrive come inviare un grande blocco di dati, ad esempio un file binario.</span><span class="sxs-lookup"><span data-stu-id="a84c9-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="a84c9-122">Considerazioni sulla sicurezza per i dati</span><span class="sxs-lookup"><span data-stu-id="a84c9-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="a84c9-123">Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="a84c9-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="a84c9-124">Panoramica dell'architettura di trasferimento dei dati</span><span class="sxs-lookup"><span data-stu-id="a84c9-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="a84c9-125">Descrive il principio generale del trasferimento dei dati in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a84c9-125">Describes a view of the overall design of data transfer in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a84c9-126">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a84c9-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="a84c9-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a84c9-127">Related Sections</span></span>  
 [<span data-ttu-id="a84c9-128">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="a84c9-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="a84c9-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a84c9-129">See Also</span></span>  
 [<span data-ttu-id="a84c9-130">Procedure consigliate: Controllo delle versioni del contratto di dati</span><span class="sxs-lookup"><span data-stu-id="a84c9-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="a84c9-131">Controllo delle versioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="a84c9-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
