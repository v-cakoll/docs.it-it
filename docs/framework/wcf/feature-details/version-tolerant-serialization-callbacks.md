---
title: Callback di serializzazione a tolleranza di versione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6e8606b8dbc0733632c2a6dc6aeb039f5277990
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="f5db8-102">Callback di serializzazione a tolleranza di versione</span><span class="sxs-lookup"><span data-stu-id="f5db8-102">Version-Tolerant Serialization Callbacks</span></span>
<span data-ttu-id="f5db8-103">Il modello di programmazione del contratto dati supporta appieno i metodi di callback della serializzazione a tolleranza di versione supportati dalle classi <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> e <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="f5db8-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="f5db8-104">Attributi a tolleranza di versione</span><span class="sxs-lookup"><span data-stu-id="f5db8-104">Version-Tolerant Attributes</span></span>  
 <span data-ttu-id="f5db8-105">Sono disponibili quattro attributi di callback.</span><span class="sxs-lookup"><span data-stu-id="f5db8-105">There are four callback attributes.</span></span> <span data-ttu-id="f5db8-106">Ogni attributo può essere applicato a un metodo che il motore di serializzazione/deserializzazione chiama in vari momenti.</span><span class="sxs-lookup"><span data-stu-id="f5db8-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="f5db8-107">Nella tabella seguente viene illustrato quando utilizzare ogni attributo.</span><span class="sxs-lookup"><span data-stu-id="f5db8-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="f5db8-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f5db8-108">Attribute</span></span>|<span data-ttu-id="f5db8-109">Quando viene chiamato il metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="f5db8-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="f5db8-110">Chiamato prima di serializzare il tipo.</span><span class="sxs-lookup"><span data-stu-id="f5db8-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="f5db8-111">Chiamato dopo aver serializzato il tipo.</span><span class="sxs-lookup"><span data-stu-id="f5db8-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="f5db8-112">Chiamato prima di deserializzare il tipo.</span><span class="sxs-lookup"><span data-stu-id="f5db8-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="f5db8-113">Chiamato dopo aver deserializzato il tipo.</span><span class="sxs-lookup"><span data-stu-id="f5db8-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="f5db8-114">I metodi devono accettare un parametro <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="f5db8-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="f5db8-115">Questi metodi sono destinati principalmente ad essere utilizzati per il controllo della versione o l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="f5db8-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="f5db8-116">Durante la deserializzazione, non viene chiamato alcun costruttore.</span><span class="sxs-lookup"><span data-stu-id="f5db8-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="f5db8-117">È quindi possibile che i membri dati non vengano inizializzati correttamente (sugli appropriati valori predefiniti) se mancano i dati per questi membri nel flusso in ingresso, ad esempio, se i dati provengono da una versione precedente di un tipo in cui mancano alcuni membri dati.</span><span class="sxs-lookup"><span data-stu-id="f5db8-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="f5db8-118">Per correggere questo problema, utilizzare il metodo di callback contrassegnato con <xref:System.Runtime.Serialization.OnDeserializingAttribute>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f5db8-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="f5db8-119">È possibile contrassegnare solo uno metodo per tipo con ognuno dei precedenti attributi di callback.</span><span class="sxs-lookup"><span data-stu-id="f5db8-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f5db8-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5db8-120">Example</span></span>  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="f5db8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5db8-121">See Also</span></span>  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [<span data-ttu-id="f5db8-122">Serializzazione a tolleranza di versione</span><span class="sxs-lookup"><span data-stu-id="f5db8-122">Version Tolerant Serialization</span></span>](../../../../docs/standard/serialization/version-tolerant-serialization.md)
