---
title: <xmlSerializer> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: b83ecda30bba8af1f3175eb6ad08593b07a80e6c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249539"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="00b6a-102">\<Elemento> xmlSerializer</span><span class="sxs-lookup"><span data-stu-id="00b6a-102">\<xmlSerializer> Element</span></span>
<span data-ttu-id="00b6a-103">Specifica se effettuare un controllo aggiuntivo dello stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="00b6a-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="00b6a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00b6a-104">\<configuration></span></span>  
<span data-ttu-id="00b6a-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="00b6a-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b6a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00b6a-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00b6a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="00b6a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="00b6a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="00b6a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00b6a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="00b6a-109">Attributes</span></span>  
  
|<span data-ttu-id="00b6a-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="00b6a-110">Attribute</span></span>|<span data-ttu-id="00b6a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b6a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00b6a-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="00b6a-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="00b6a-113">Specifica se controllare lo stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="00b6a-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="00b6a-114">Impostare l'attributo su "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="00b6a-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="00b6a-115">Il valore predefinito è "true".</span><span class="sxs-lookup"><span data-stu-id="00b6a-115">The default is "true".</span></span>|  
|<span data-ttu-id="00b6a-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="00b6a-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="00b6a-117">Specifica se <xref:System.Xml.Serialization.XmlSerializer> usa la generazione legacy di serializzazione che genera assembly scrivendo un codice C# in un file e quindi compilandola in un assembly.</span><span class="sxs-lookup"><span data-stu-id="00b6a-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="00b6a-118">Il valore predefinito è **false**.</span><span class="sxs-lookup"><span data-stu-id="00b6a-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00b6a-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="00b6a-119">Child Elements</span></span>  
 <span data-ttu-id="00b6a-120">No.</span><span class="sxs-lookup"><span data-stu-id="00b6a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00b6a-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="00b6a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="00b6a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b6a-122">Element</span></span>|<span data-ttu-id="00b6a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b6a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00b6a-124">\<Elemento> system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="00b6a-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="00b6a-125">Contiene le impostazioni di configurazione per le classi <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="00b6a-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00b6a-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="00b6a-126">Remarks</span></span>  
 <span data-ttu-id="00b6a-127">Per impostazione predefinita, <xref:System.Xml.Serialization.XmlSerializer> fornisce un livello aggiuntivo di sicurezza contro potenziali attacchi di tipo Denial of Service durante la deserializzazione di dati non attendibili.</span><span class="sxs-lookup"><span data-stu-id="00b6a-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="00b6a-128">Per ottenere questo risultato, tenta di rilevare cicli infiniti durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="00b6a-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="00b6a-129">Se tale condizione viene rilevata, viene generata un'eccezione con un messaggio che comunica che a causa di un errore interno la deserializzazione non può passare al flusso sottostante.</span><span class="sxs-lookup"><span data-stu-id="00b6a-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="00b6a-130">Se si riceve questo messaggio, non significa che è necessariamente in corso un attacco di tipo Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="00b6a-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="00b6a-131">In rare circostanze, il meccanismo di rilevamento di ciclo infinito produce un falso positivo e l'eccezione viene generata pur trattandosi di un un messaggio in arrivo valido.</span><span class="sxs-lookup"><span data-stu-id="00b6a-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="00b6a-132">Nel caso in cui i messaggi validi della propria applicazione vengano rifiutati da tale livello aggiuntivo di protezione, impostare l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="00b6a-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b6a-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="00b6a-133">Example</span></span>  
 <span data-ttu-id="00b6a-134">L'esempio seguente imposta l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="00b6a-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00b6a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00b6a-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="00b6a-136">\<Elemento> system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="00b6a-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="00b6a-137">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="00b6a-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
