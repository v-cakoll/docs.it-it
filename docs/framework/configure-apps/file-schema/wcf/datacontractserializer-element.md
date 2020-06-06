---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400443"
---
# \<dataContractSerializer>
<span data-ttu-id="c05df-101">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c05df-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="c05df-102">Questo elemento è presente in due gerarchie diverse</span><span class="sxs-lookup"><span data-stu-id="c05df-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="c05df-103">e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="c05df-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="c05df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c05df-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c05df-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c05df-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c05df-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c05df-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c05df-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c05df-107">Attributes</span></span>  
  
|<span data-ttu-id="c05df-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="c05df-108">Element</span></span>|<span data-ttu-id="c05df-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c05df-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c05df-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c05df-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="c05df-111">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="c05df-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="c05df-112">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="c05df-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="c05df-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c05df-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="c05df-114">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="c05df-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="c05df-115">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="c05df-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c05df-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c05df-116">Child Elements</span></span>  
 <span data-ttu-id="c05df-117">No.</span><span class="sxs-lookup"><span data-stu-id="c05df-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c05df-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c05df-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c05df-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c05df-119">Element</span></span>|<span data-ttu-id="c05df-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c05df-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="c05df-121">Raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="c05df-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="c05df-122">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c05df-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c05df-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="c05df-123">Remarks</span></span>  
 <span data-ttu-id="c05df-124">Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui \<X509Extension> si verifica l'elemento.</span><span class="sxs-lookup"><span data-stu-id="c05df-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="c05df-125">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c05df-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05df-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c05df-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="c05df-127">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="c05df-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="c05df-128">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="c05df-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
