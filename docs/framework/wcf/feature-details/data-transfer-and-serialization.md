---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 1eefd82a149d0bc215ca441e92c7d737a744b1e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088405"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="6ac7c-102">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="6ac7c-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="6ac7c-103">In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="6ac7c-104">Gli sviluppatori di un servizio o client, è necessario comprendere come Windows Communication Foundation (WCF) gestisce i dati e la serializzazione dei dati per creare applicazioni che sono efficienti e facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ac7c-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="6ac7c-105">In This Section</span></span>  
 [<span data-ttu-id="6ac7c-106">Specifica del trasferimento di dati nei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="6ac7c-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="6ac7c-107">Descrive i concetti di base del trasferimento dati nei servizi.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="6ac7c-108">Uso di contratti dati</span><span class="sxs-lookup"><span data-stu-id="6ac7c-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="6ac7c-109">Descrive i contratti dati, come crearli e utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="6ac7c-110">Serializzatore dei contratti dati</span><span class="sxs-lookup"><span data-stu-id="6ac7c-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="6ac7c-111">Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="6ac7c-112">Utilizzo della classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="6ac7c-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="6ac7c-113">Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="6ac7c-114">Utilizzo dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="6ac7c-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="6ac7c-115">Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="6ac7c-116">Utilizzo della classe Message</span><span class="sxs-lookup"><span data-stu-id="6ac7c-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="6ac7c-117">Descrive come utilizzare le funzionalità di una classe Message.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="6ac7c-118">Filtro</span><span class="sxs-lookup"><span data-stu-id="6ac7c-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="6ac7c-119">Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="6ac7c-120">Dati di grandi dimensioni e flussi</span><span class="sxs-lookup"><span data-stu-id="6ac7c-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="6ac7c-121">Descrive come inviare un grande blocco di dati, ad esempio un file binario.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="6ac7c-122">Considerazioni sulla protezione per i dati</span><span class="sxs-lookup"><span data-stu-id="6ac7c-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="6ac7c-123">Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="6ac7c-124">Panoramica dell'architettura di trasferimento dei dati</span><span class="sxs-lookup"><span data-stu-id="6ac7c-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="6ac7c-125">Descrive una vista della progettazione complessiva del trasferimento dei dati in WCF.</span><span class="sxs-lookup"><span data-stu-id="6ac7c-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6ac7c-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6ac7c-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="6ac7c-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6ac7c-127">Related Sections</span></span>  
 [<span data-ttu-id="6ac7c-128">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="6ac7c-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ac7c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ac7c-129">See also</span></span>

- [<span data-ttu-id="6ac7c-130">Procedure consigliate: Controllo delle versioni dei contratti dati</span><span class="sxs-lookup"><span data-stu-id="6ac7c-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [<span data-ttu-id="6ac7c-131">Controllo delle versioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="6ac7c-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
