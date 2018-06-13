---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 53c1421bf14c598611e116c61353c4ecd465f1aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489206"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="9fc71-102">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="9fc71-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="9fc71-103">In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati.</span><span class="sxs-lookup"><span data-stu-id="9fc71-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="9fc71-104">Gli sviluppatori di un servizio o client, è necessario comprendere come Windows Communication Foundation (WCF) gestisce dati e la serializzazione dei dati per poter creare applicazioni efficienti e facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="9fc71-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9fc71-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9fc71-105">In This Section</span></span>  
 [<span data-ttu-id="9fc71-106">Definizione del trasferimento dati nei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="9fc71-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="9fc71-107">Descrive i concetti di base del trasferimento dati nei servizi.</span><span class="sxs-lookup"><span data-stu-id="9fc71-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="9fc71-108">Uso di contratti di dati</span><span class="sxs-lookup"><span data-stu-id="9fc71-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="9fc71-109">Descrive i contratti dati, come crearli e utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="9fc71-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="9fc71-110">Serializzatore dei contratti di dati</span><span class="sxs-lookup"><span data-stu-id="9fc71-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="9fc71-111">Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9fc71-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="9fc71-112">Uso della classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="9fc71-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="9fc71-113">Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9fc71-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="9fc71-114">Uso di contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="9fc71-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="9fc71-115">Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="9fc71-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="9fc71-116">Uso della classe Message</span><span class="sxs-lookup"><span data-stu-id="9fc71-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="9fc71-117">Descrive come utilizzare le funzionalità di una classe Message.</span><span class="sxs-lookup"><span data-stu-id="9fc71-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="9fc71-118">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="9fc71-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="9fc71-119">Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.</span><span class="sxs-lookup"><span data-stu-id="9fc71-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="9fc71-120">Dati di grandi dimensioni e streaming</span><span class="sxs-lookup"><span data-stu-id="9fc71-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="9fc71-121">Descrive come inviare un grande blocco di dati, ad esempio un file binario.</span><span class="sxs-lookup"><span data-stu-id="9fc71-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="9fc71-122">Considerazioni sulla sicurezza per i dati</span><span class="sxs-lookup"><span data-stu-id="9fc71-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="9fc71-123">Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="9fc71-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="9fc71-124">Panoramica dell'architettura di trasferimento dati</span><span class="sxs-lookup"><span data-stu-id="9fc71-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="9fc71-125">Descrive una visualizzazione della struttura complessiva di trasferimento dei dati in WCF.</span><span class="sxs-lookup"><span data-stu-id="9fc71-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9fc71-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="9fc71-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="9fc71-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9fc71-127">Related Sections</span></span>  
 [<span data-ttu-id="9fc71-128">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="9fc71-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="9fc71-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fc71-129">See Also</span></span>  
 [<span data-ttu-id="9fc71-130">Procedure consigliate: Controllo delle versioni del contratto di dati</span><span class="sxs-lookup"><span data-stu-id="9fc71-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="9fc71-131">Controllo delle versioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="9fc71-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
