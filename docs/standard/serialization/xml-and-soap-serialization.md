---
title: Serializzazione SOAP e XML
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: d9dc68d8e7eced031af404aaec20784573c9930a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028239"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="11abe-102">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="11abe-102">XML and SOAP Serialization</span></span>

<span data-ttu-id="11abe-103">La serializzazione XML converte (serializza) le proprietà e i campi pubblici di un oggetto, o i parametri e i valori restituiti dei metodi, in un flusso XML conforme a uno specifico documento in linguaggio XSD (XML Schema Definition).</span><span class="sxs-lookup"><span data-stu-id="11abe-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="11abe-104">La serializzazione XML produce classi fortemente tipizzate con campi e proprietà pubbliche convertiti in un formato seriale (in questo caso XML) per l'archiviazione o il trasporto.</span><span class="sxs-lookup"><span data-stu-id="11abe-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="11abe-105">Dal momento che XML è uno standard aperto, il flusso XML può essere elaborato da qualsiasi applicazione, in base alle necessità, indipendentemente dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="11abe-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="11abe-106">Ad esempio, i servizi Web XML creati tramite ASP.NET, utilizzano la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML che passano dati tra applicazioni del servizio Web XML tramite Internet o sulle Intranet.</span><span class="sxs-lookup"><span data-stu-id="11abe-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="11abe-107">Al contrario, la deserializzazione prende tale flusso XML e ricostruisce l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="11abe-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="11abe-108">La serializzazione XML può essere utilizzata anche per serializzare oggetti nei flussi XML conformi alla specifica SOAP.</span><span class="sxs-lookup"><span data-stu-id="11abe-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="11abe-109">Il SOAP è un protocollo basato su XML, specificamente progettato per trasportare chiamate di routine mediante XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="11abe-110">Per serializzare o deserializzare oggetti, utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="11abe-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="11abe-111">Per creare le classi da serializzare, utilizzare lo strumento XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="11abe-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="11abe-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="11abe-112">In This Section</span></span>

[<span data-ttu-id="11abe-113">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="11abe-113">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)  
<span data-ttu-id="11abe-114">Fornisce una definizione generale di serializzazione, in modo particolare della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-114">Provides a general definition of serialization, particularly XML serialization.</span></span>

[<span data-ttu-id="11abe-115">Procedura: Serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="11abe-115">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)  
<span data-ttu-id="11abe-116">Vengono fornite istruzioni dettagliate per la serializzazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="11abe-116">Provides step-by-step instructions for serializing an object.</span></span>

[<span data-ttu-id="11abe-117">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="11abe-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)  
<span data-ttu-id="11abe-118">Vengono fornite istruzioni dettagliate per la deserializzazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="11abe-118">Provides step-by-step instructions for deserializing an object.</span></span>

[<span data-ttu-id="11abe-119">Esempi di serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="11abe-119">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)  
<span data-ttu-id="11abe-120">Fornisce esempi che dimostrano le funzioni di base della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-120">Provides examples that demonstrate the basics of XML serialization.</span></span>

[<span data-ttu-id="11abe-121">Strumento XML Schema Definition e serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="11abe-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)  
<span data-ttu-id="11abe-122">Descrive come utilizzare lo strumento XML Schema Definition per creare classi conformi a un determinato schema XSD (XML Schema Definition) o generare uno schema XML da un file dll.</span><span class="sxs-lookup"><span data-stu-id="11abe-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>

[<span data-ttu-id="11abe-123">Controllo della serializzazione XML mediante attributi</span><span class="sxs-lookup"><span data-stu-id="11abe-123">Controlling XML Serialization Using Attributes</span></span>](controlling-xml-serialization-using-attributes.md)  
<span data-ttu-id="11abe-124">Descrive come controllare la serializzazione tramite l'utilizzo di attributi.</span><span class="sxs-lookup"><span data-stu-id="11abe-124">Describes how to control serialization by using attributes.</span></span>

[<span data-ttu-id="11abe-125">Attributi per il controllo della serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="11abe-125">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)  
<span data-ttu-id="11abe-126">Elenca gli attributi utilizzati per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-126">Lists the attributes that are used to control XML serialization.</span></span>

[<span data-ttu-id="11abe-127">Procedura: Specificare un nome di elemento alternativo per un Stream XML</span><span class="sxs-lookup"><span data-stu-id="11abe-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
<span data-ttu-id="11abe-128">Presenta uon scenario avanzato in cui viene illustrato come generare più flussi XML eseguendo l'override della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="11abe-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>

[<span data-ttu-id="11abe-129">Procedura: Controllare la serializzazione delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="11abe-129">How to: Control Serialization of Derived Classes</span></span>](how-to-control-serialization-of-derived-classes.md)  
<span data-ttu-id="11abe-130">Viene fornito un esempio in cui viene illustrato come controllare la serializzazione di classi derivate.</span><span class="sxs-lookup"><span data-stu-id="11abe-130">Provides an example of how to control the serialization of derived classes.</span></span>

[<span data-ttu-id="11abe-131">Procedura: Qualificare nomi di attributi ed elementi XML</span><span class="sxs-lookup"><span data-stu-id="11abe-131">How to: Qualify XML Element and XML Attribute Names</span></span>](how-to-qualify-xml-element-and-xml-attribute-names.md)  
<span data-ttu-id="11abe-132">Descrive come definire e controllare il modo in cui gli spazi dei nomi XML vengono utilizzati nel flusso XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>

[<span data-ttu-id="11abe-133">Serializzazione XML con Servizi Web XML</span><span class="sxs-lookup"><span data-stu-id="11abe-133">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)  
<span data-ttu-id="11abe-134">Spiega in che modo la serializzazione XML viene utilizzata nei servizi Web XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-134">Explains how XML serialization is used in XML Web services.</span></span>

[<span data-ttu-id="11abe-135">Procedura: Serializzare un oggetto come un Stream XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="11abe-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
<span data-ttu-id="11abe-136">Viene descritto come utilizzare il <xref:System.Xml.Serialization.XmlSerializer> classe per creare flussi XML SOAP codificati conformi alla sezione 5 del documento del World Wide Web Consortium (W3C) intitolato [SOAP Simple Object Access Protocol () 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span><span class="sxs-lookup"><span data-stu-id="11abe-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span></span>

[<span data-ttu-id="11abe-137">Procedura: Eseguire l'override della serializzazione XML con codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="11abe-137">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)  
<span data-ttu-id="11abe-138">Descrive il processo per l'esecuzione dell'override della serializzazione XML di oggetti come messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="11abe-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>

[<span data-ttu-id="11abe-139">Attributi per il controllo della serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="11abe-139">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)  
<span data-ttu-id="11abe-140">Elenca gli attributi utilizzati per il controllo della serializzazione con codifica SOAP.</span><span class="sxs-lookup"><span data-stu-id="11abe-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>

[<span data-ttu-id="11abe-141">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="11abe-141">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)  
<span data-ttu-id="11abe-142">La configurazione di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="11abe-142">The top-level configuration element for controlling XML serialization.</span></span>

[<span data-ttu-id="11abe-143">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="11abe-143">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)  
<span data-ttu-id="11abe-144">Controlla la modalità della serializzazione di oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="11abe-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>

[<span data-ttu-id="11abe-145">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="11abe-145">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)  
<span data-ttu-id="11abe-146">Contiene i tipi usati dalla classe <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="11abe-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

[<span data-ttu-id="11abe-147">\<aggiungere > (elemento) per \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="11abe-147">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)  
<span data-ttu-id="11abe-148">Aggiunge i tipi usati dalla classe <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="11abe-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

## <a name="related-sections"></a><span data-ttu-id="11abe-149">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="11abe-149">Related Sections</span></span>

<span data-ttu-id="11abe-150">[Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11abe-150">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>  
<span data-ttu-id="11abe-151">Fornisce gli argomenti che descrivono e spiegano come programmare i servizi Web XML con ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="11abe-151">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="11abe-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11abe-152">See also</span></span>

- [<span data-ttu-id="11abe-153">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="11abe-153">Binary Serialization</span></span>](binary-serialization.md)
