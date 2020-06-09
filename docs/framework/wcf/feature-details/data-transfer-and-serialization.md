---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: b07937b0a94c24a934b17d6cf21b726ee0d4362e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593487"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="1d383-102">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="1d383-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="1d383-103">In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati.</span><span class="sxs-lookup"><span data-stu-id="1d383-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="1d383-104">In qualità di sviluppatore di un servizio o di un client, è inoltre necessario comprendere il modo in cui Windows Communication Foundation (WCF) gestisce i dati e la serializzazione dei dati per creare applicazioni efficienti e facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="1d383-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d383-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1d383-105">In This Section</span></span>  
 [<span data-ttu-id="1d383-106">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="1d383-106">Specifying Data Transfer in Service Contracts</span></span>](specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="1d383-107">Descrive i concetti di base del trasferimento dati nei servizi.</span><span class="sxs-lookup"><span data-stu-id="1d383-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="1d383-108">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="1d383-108">Using Data Contracts</span></span>](using-data-contracts.md)  
 <span data-ttu-id="1d383-109">Descrive i contratti dati, come crearli e utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="1d383-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="1d383-110">Serializzatore dei contratti dati</span><span class="sxs-lookup"><span data-stu-id="1d383-110">Data Contract Serializer</span></span>](data-contract-serializer.md)  
 <span data-ttu-id="1d383-111">Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1d383-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="1d383-112">Utilizzo della classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="1d383-112">Using the XmlSerializer Class</span></span>](using-the-xmlserializer-class.md)  
 <span data-ttu-id="1d383-113">Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1d383-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="1d383-114">Utilizzo dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="1d383-114">Using Message Contracts</span></span>](using-message-contracts.md)  
 <span data-ttu-id="1d383-115">Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="1d383-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="1d383-116">Utilizzo della classe Message</span><span class="sxs-lookup"><span data-stu-id="1d383-116">Using the Message Class</span></span>](using-the-message-class.md)  
 <span data-ttu-id="1d383-117">Descrive come utilizzare le funzionalità di una classe Message.</span><span class="sxs-lookup"><span data-stu-id="1d383-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="1d383-118">Filtro</span><span class="sxs-lookup"><span data-stu-id="1d383-118">Filtering</span></span>](filtering.md)  
 <span data-ttu-id="1d383-119">Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.</span><span class="sxs-lookup"><span data-stu-id="1d383-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="1d383-120">Flussi e dati di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="1d383-120">Large Data and Streaming</span></span>](large-data-and-streaming.md)  
 <span data-ttu-id="1d383-121">Descrive come inviare un grande blocco di dati, ad esempio un file binario.</span><span class="sxs-lookup"><span data-stu-id="1d383-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="1d383-122">Considerazioni sulla sicurezza per i dati</span><span class="sxs-lookup"><span data-stu-id="1d383-122">Security Considerations for Data</span></span>](security-considerations-for-data.md)  
 <span data-ttu-id="1d383-123">Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="1d383-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="1d383-124">Panoramica dell'architettura di trasferimento dei dati</span><span class="sxs-lookup"><span data-stu-id="1d383-124">Data Transfer Architectural Overview</span></span>](data-transfer-architectural-overview.md)  
 <span data-ttu-id="1d383-125">Viene descritta una visualizzazione della progettazione complessiva del trasferimento dei dati in WCF.</span><span class="sxs-lookup"><span data-stu-id="1d383-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1d383-126">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="1d383-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="1d383-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1d383-127">Related Sections</span></span>  
 [<span data-ttu-id="1d383-128">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="1d383-128">Extending Encoders and Serializers</span></span>](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d383-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d383-129">See also</span></span>

- [<span data-ttu-id="1d383-130">Procedure consigliate: controllo delle versioni del contratto dati</span><span class="sxs-lookup"><span data-stu-id="1d383-130">Best Practices: Data Contract Versioning</span></span>](../best-practices-data-contract-versioning.md)
- [<span data-ttu-id="1d383-131">Controllo delle versioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="1d383-131">Service Versioning</span></span>](../service-versioning.md)
