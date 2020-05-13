---
title: <xmlSerializer> Elemento
description: L' <xmlSerializer> elemento specifica se è stato eseguito un ulteriore controllo dello stato di XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 68037959893ec307a896ea86d21e40a9d7aa824c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380029"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="8893d-103">\<Elemento> XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="8893d-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="8893d-104">Specifica se effettuare un controllo aggiuntivo dello stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8893d-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="8893d-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8893d-105">\<configuration></span></span>  
<span data-ttu-id="8893d-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="8893d-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8893d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8893d-107">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8893d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8893d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8893d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8893d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8893d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="8893d-110">Attributes</span></span>  
  
|<span data-ttu-id="8893d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="8893d-111">Attribute</span></span>|<span data-ttu-id="8893d-112">Description</span><span class="sxs-lookup"><span data-stu-id="8893d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8893d-113">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="8893d-113">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="8893d-114">Specifica se controllare lo stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8893d-114">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="8893d-115">Impostare l'attributo su "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="8893d-115">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="8893d-116">Il valore predefinito è "true".</span><span class="sxs-lookup"><span data-stu-id="8893d-116">The default is "true".</span></span>|  
|<span data-ttu-id="8893d-117">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="8893d-117">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="8893d-118">Specifica se <xref:System.Xml.Serialization.XmlSerializer> usa la generazione legacy di serializzazione che genera assembly scrivendo un codice C# in un file e quindi compilandola in un assembly.</span><span class="sxs-lookup"><span data-stu-id="8893d-118">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="8893d-119">Il valore predefinito è **false**.</span><span class="sxs-lookup"><span data-stu-id="8893d-119">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8893d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8893d-120">Child Elements</span></span>  
 <span data-ttu-id="8893d-121">No.</span><span class="sxs-lookup"><span data-stu-id="8893d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8893d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8893d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8893d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8893d-123">Element</span></span>|<span data-ttu-id="8893d-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8893d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8893d-125">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="8893d-125">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="8893d-126">Contiene le impostazioni di configurazione per le classi <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="8893d-126">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8893d-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8893d-127">Remarks</span></span>  
 <span data-ttu-id="8893d-128">Per impostazione predefinita, <xref:System.Xml.Serialization.XmlSerializer> fornisce un livello aggiuntivo di sicurezza contro potenziali attacchi di tipo Denial of Service durante la deserializzazione di dati non attendibili.</span><span class="sxs-lookup"><span data-stu-id="8893d-128">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="8893d-129">Per ottenere questo risultato, tenta di rilevare cicli infiniti durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="8893d-129">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="8893d-130">Se tale condizione viene rilevata, viene generata un'eccezione con un messaggio che comunica che a causa di un errore interno la deserializzazione non può passare al flusso sottostante.</span><span class="sxs-lookup"><span data-stu-id="8893d-130">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="8893d-131">Se si riceve questo messaggio, non significa che è necessariamente in corso un attacco di tipo Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="8893d-131">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="8893d-132">In rare circostanze, il meccanismo di rilevamento di ciclo infinito produce un falso positivo e l'eccezione viene generata pur trattandosi di un un messaggio in arrivo valido.</span><span class="sxs-lookup"><span data-stu-id="8893d-132">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="8893d-133">Nel caso in cui i messaggi validi della propria applicazione vengano rifiutati da tale livello aggiuntivo di protezione, impostare l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="8893d-133">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="8893d-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="8893d-134">Example</span></span>  
 <span data-ttu-id="8893d-135">L'esempio seguente imposta l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="8893d-135">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8893d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8893d-136">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="8893d-137">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="8893d-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="8893d-138">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="8893d-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
