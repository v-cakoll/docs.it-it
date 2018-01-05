---
title: Attributi per il controllo della serializzazione SOAP codificata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae3193a2f9ef01f8e7f71235f15ed070e84ec11c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="4ef72-102">Attributi per il controllo della serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="4ef72-102">Attributes That Control Encoded SOAP Serialization</span></span> 
<span data-ttu-id="4ef72-103">Il documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium (www.w3.org) contiene una sezione facoltativa (la sezione 5) che descrive le modalità di codifica dei parametri SOAP.</span><span class="sxs-lookup"><span data-stu-id="4ef72-103">The World Wide Web Consortium (www.w3.org) document named "Simple Object Access Protocol (SOAP) 1.1" contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="4ef72-104">Per ottenere la conformità alla sezione 5 delle specifiche, è necessario usare un set speciale di attributi reperibile nello spazio dei nomi <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="4ef72-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="4ef72-105">Applicare tali attributi nel modo appropriato alle classi e ai membri delle classi, quindi utilizzare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le istanze della classe o delle classi.</span><span class="sxs-lookup"><span data-stu-id="4ef72-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>  
  
 <span data-ttu-id="4ef72-106">Nella seguente tabella sono illustrati gli attributi, dove è possibile applicarli e la loro funzione.</span><span class="sxs-lookup"><span data-stu-id="4ef72-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="4ef72-107">Per altre informazioni sull'utilizzo di questi attributi per il controllo della serializzazione XML, vedere [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) e [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="4ef72-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span></span>  
  
 <span data-ttu-id="4ef72-108">Per altre informazioni sugli attributi, vedere [Attributi](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="4ef72-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>  
  
|<span data-ttu-id="4ef72-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ef72-109">Attribute</span></span>|<span data-ttu-id="4ef72-110">Si applica a</span><span class="sxs-lookup"><span data-stu-id="4ef72-110">Applies to</span></span>|<span data-ttu-id="4ef72-111">Specifica</span><span class="sxs-lookup"><span data-stu-id="4ef72-111">Specifies</span></span>|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="4ef72-112">Campo pubblico, proprietà, parametro o valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4ef72-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="4ef72-113">Il membro della classe sarà serializzato come attributo XML.</span><span class="sxs-lookup"><span data-stu-id="4ef72-113">The class member will be serialized as an XML attribute.</span></span>|  
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="4ef72-114">Campo pubblico, proprietà, parametro o valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4ef72-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="4ef72-115">La classe verrà serializzata come elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4ef72-115">The class will be serialized as an XML element.</span></span>|  
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="4ef72-116">Campo pubblico che rappresenta un identificatore dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4ef72-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="4ef72-117">Il nome dell'elemento di un membro dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4ef72-117">The element name of an enumeration member.</span></span>|  
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="4ef72-118">Proprietà e campi pubblici</span><span class="sxs-lookup"><span data-stu-id="4ef72-118">Public properties and fields.</span></span>|<span data-ttu-id="4ef72-119">La proprietà o il campo devono essere ignorati se la classe che li contiene è serializzata.</span><span class="sxs-lookup"><span data-stu-id="4ef72-119">The property or field should be ignored when the containing class is serialized.</span></span>|  
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="4ef72-120">Dichiarazioni della classe derivata pubblica e metodi pubblici per i documenti del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="4ef72-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="4ef72-121">Il tipo deve essere incluso durante la generazione degli schemi (per essere riconosciuto se serializzato).</span><span class="sxs-lookup"><span data-stu-id="4ef72-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|  
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="4ef72-122">Dichiarazioni di classe pubblica</span><span class="sxs-lookup"><span data-stu-id="4ef72-122">Public class declarations.</span></span>|<span data-ttu-id="4ef72-123">La classe deve essere serializzata come un tipo XML.</span><span class="sxs-lookup"><span data-stu-id="4ef72-123">The class should be serialized as an XML type.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ef72-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef72-124">See Also</span></span>  
 [<span data-ttu-id="4ef72-125">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="4ef72-125">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="4ef72-126">Procedura: Serializzare un oggetto come flusso XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="4ef72-126">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 [<span data-ttu-id="4ef72-127">Procedura: Eseguire l'override della serializzazione XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="4ef72-127">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 [<span data-ttu-id="4ef72-128">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ef72-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="4ef72-129">Procedura: Serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="4ef72-129">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="4ef72-130">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="4ef72-130">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
