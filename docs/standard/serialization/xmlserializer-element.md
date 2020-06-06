---
title: <xmlSerializer> Elemento
description: L' <xmlSerializer> elemento specifica se è stato eseguito un ulteriore controllo dello stato di XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 667d59f7eb0d1c7682afcdda584cc5b0ca2da802
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288927"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="1ebce-103">\<xmlSerializer> Elemento</span><span class="sxs-lookup"><span data-stu-id="1ebce-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="1ebce-104">Specifica se effettuare un controllo aggiuntivo dello stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1ebce-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="1ebce-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ebce-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ebce-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ebce-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1ebce-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ebce-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ebce-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ebce-108">Attributes</span></span>  
  
|<span data-ttu-id="1ebce-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ebce-109">Attribute</span></span>|<span data-ttu-id="1ebce-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ebce-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ebce-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="1ebce-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="1ebce-112">Specifica se controllare lo stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1ebce-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="1ebce-113">Impostare l'attributo su "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="1ebce-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="1ebce-114">Il valore predefinito è "true".</span><span class="sxs-lookup"><span data-stu-id="1ebce-114">The default is "true".</span></span>|  
|<span data-ttu-id="1ebce-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="1ebce-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="1ebce-116">Specifica se <xref:System.Xml.Serialization.XmlSerializer> usa la generazione legacy di serializzazione che genera assembly scrivendo un codice C# in un file e quindi compilandola in un assembly.</span><span class="sxs-lookup"><span data-stu-id="1ebce-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="1ebce-117">Il valore predefinito è **false**.</span><span class="sxs-lookup"><span data-stu-id="1ebce-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ebce-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ebce-118">Child Elements</span></span>  
 <span data-ttu-id="1ebce-119">No.</span><span class="sxs-lookup"><span data-stu-id="1ebce-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ebce-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ebce-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1ebce-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ebce-121">Element</span></span>|<span data-ttu-id="1ebce-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ebce-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ebce-123">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="1ebce-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="1ebce-124">Contiene le impostazioni di configurazione per le classi <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="1ebce-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ebce-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ebce-125">Remarks</span></span>  
 <span data-ttu-id="1ebce-126">Per impostazione predefinita, <xref:System.Xml.Serialization.XmlSerializer> fornisce un livello aggiuntivo di sicurezza contro potenziali attacchi di tipo Denial of Service durante la deserializzazione di dati non attendibili.</span><span class="sxs-lookup"><span data-stu-id="1ebce-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="1ebce-127">Per ottenere questo risultato, tenta di rilevare cicli infiniti durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="1ebce-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="1ebce-128">Se tale condizione viene rilevata, viene generata un'eccezione con un messaggio che comunica che a causa di un errore interno la deserializzazione non può passare al flusso sottostante.</span><span class="sxs-lookup"><span data-stu-id="1ebce-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="1ebce-129">Se si riceve questo messaggio, non significa che è necessariamente in corso un attacco di tipo Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="1ebce-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="1ebce-130">In rare circostanze, il meccanismo di rilevamento di ciclo infinito produce un falso positivo e l'eccezione viene generata pur trattandosi di un un messaggio in arrivo valido.</span><span class="sxs-lookup"><span data-stu-id="1ebce-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="1ebce-131">Nel caso in cui i messaggi validi della propria applicazione vengano rifiutati da tale livello aggiuntivo di protezione, impostare l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="1ebce-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ebce-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ebce-132">Example</span></span>  
 <span data-ttu-id="1ebce-133">L'esempio seguente imposta l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="1ebce-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ebce-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1ebce-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="1ebce-135">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="1ebce-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="1ebce-136">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="1ebce-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
