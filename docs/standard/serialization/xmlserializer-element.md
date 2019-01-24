---
title: Elemento &lt;xmlSerializer&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 4b511dc229c9e8321b91fbb0f9395627680e5d12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591955"
---
# <a name="ltxmlserializergt-element"></a><span data-ttu-id="b9f5d-102">Elemento &lt;xmlSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="b9f5d-102">&lt;xmlSerializer&gt; Element</span></span>
<span data-ttu-id="b9f5d-103">Specifica se effettuare un controllo aggiuntivo dello stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="b9f5d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b9f5d-104">\<configuration></span></span>  
<span data-ttu-id="b9f5d-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b9f5d-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f5d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9f5d-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9f5d-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b9f5d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b9f5d-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9f5d-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="b9f5d-109">Attributes</span></span>  
  
|<span data-ttu-id="b9f5d-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="b9f5d-110">Attribute</span></span>|<span data-ttu-id="b9f5d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9f5d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9f5d-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="b9f5d-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="b9f5d-113">Specifica se controllare lo stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="b9f5d-114">Impostare l'attributo su "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="b9f5d-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="b9f5d-115">Il valore predefinito è "true".</span><span class="sxs-lookup"><span data-stu-id="b9f5d-115">The default is "true".</span></span>|  
|<span data-ttu-id="b9f5d-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="b9f5d-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="b9f5d-117">Specifica se <xref:System.Xml.Serialization.XmlSerializer> usa la generazione legacy di serializzazione che genera assembly scrivendo un codice C# in un file e quindi compilandola in un assembly.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="b9f5d-118">Il valore predefinito è **false**.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9f5d-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b9f5d-119">Child Elements</span></span>  
 <span data-ttu-id="b9f5d-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9f5d-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b9f5d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b9f5d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9f5d-122">Element</span></span>|<span data-ttu-id="b9f5d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9f5d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9f5d-124">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b9f5d-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="b9f5d-125">Contiene le impostazioni di configurazione per le classi <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9f5d-126">Note</span><span class="sxs-lookup"><span data-stu-id="b9f5d-126">Remarks</span></span>  
 <span data-ttu-id="b9f5d-127">Per impostazione predefinita, <xref:System.Xml.Serialization.XmlSerializer> fornisce un livello aggiuntivo di sicurezza contro potenziali attacchi di tipo Denial of Service durante la deserializzazione di dati non attendibili.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="b9f5d-128">Per ottenere questo risultato, tenta di rilevare cicli infiniti durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="b9f5d-129">Se viene rilevata questa condizione, viene generata un'eccezione con messaggio analogo al seguente: "Errore interno: la deserializzazione non può passare al flusso sottostante."</span><span class="sxs-lookup"><span data-stu-id="b9f5d-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="b9f5d-130">Se si riceve questo messaggio, non significa che è necessariamente in corso un attacco di tipo Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="b9f5d-131">In rare circostanze, il meccanismo di rilevamento di ciclo infinito produce un falso positivo e l'eccezione viene generata pur trattandosi di un messaggio in arrivo valido.</span><span class="sxs-lookup"><span data-stu-id="b9f5d-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="b9f5d-132">Nel caso in cui i messaggi validi della propria applicazione vengano rifiutati da tale livello aggiuntivo di protezione, impostare l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="b9f5d-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9f5d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f5d-133">Example</span></span>  
 <span data-ttu-id="b9f5d-134">L'esempio seguente imposta l'attributo **checkDeserializeAdvances** su "false".</span><span class="sxs-lookup"><span data-stu-id="b9f5d-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9f5d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9f5d-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="b9f5d-136">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b9f5d-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="b9f5d-137">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="b9f5d-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
