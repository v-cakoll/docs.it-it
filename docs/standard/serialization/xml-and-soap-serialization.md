---
title: Serializzazione SOAP e XML
description: In questa panoramica viene illustrata la serializzazione XML, che può essere utilizzata per serializzare oggetti in flussi XML conformi alla specifica SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: 6b7d6f59694a28207758fa7772781eed073917e4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "83379536"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="fc5cc-103">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="fc5cc-103">XML and SOAP serialization</span></span>

<span data-ttu-id="fc5cc-104">La serializzazione XML converte (serializza) i campi pubblici e le proprietà di un oggetto, nonché i parametri e i valori restituiti dei metodi, in un flusso XML conforme a un documento XSD (XML Schema Definition Language) specifico.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-104">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="fc5cc-105">La serializzazione XML produce classi fortemente tipizzate con campi e proprietà pubbliche convertiti in un formato seriale (in questo caso XML) per l'archiviazione o il trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-105">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="fc5cc-106">Dal momento che XML è uno standard aperto, il flusso XML può essere elaborato da qualsiasi applicazione, in base alle necessità, indipendentemente dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-106">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="fc5cc-107">Ad esempio, i servizi Web XML creati tramite ASP.NET, utilizzano la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML che passano dati tra applicazioni del servizio Web XML tramite Internet o sulle Intranet.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-107">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="fc5cc-108">Al contrario, la deserializzazione prende tale flusso XML e ricostruisce l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-108">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="fc5cc-109">La serializzazione XML può essere utilizzata anche per serializzare oggetti nei flussi XML conformi alla specifica SOAP.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-109">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="fc5cc-110">Il SOAP è un protocollo basato su XML, specificamente progettato per trasportare chiamate di routine mediante XML.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-110">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="fc5cc-111">Per serializzare o deserializzare oggetti, utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-111">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="fc5cc-112">Per creare le classi da serializzare, utilizzare lo strumento XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="fc5cc-112">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc5cc-113">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fc5cc-113">See also</span></span>

- [<span data-ttu-id="fc5cc-114">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="fc5cc-114">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="fc5cc-115">[Servizi Web XML creati con ASP.NET e client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fc5cc-115">[XML Web Services created using ASP.NET and XML Web Service clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
