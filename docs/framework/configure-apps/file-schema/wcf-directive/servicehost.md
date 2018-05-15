---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: f81c71746b6b59a51ee825b44c9e6d9f93eb5fbd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="67283-101">Associa la factory usata per creare l'host del servizio al servizio da ospitare e agli altri aspetti di programmazione necessari per accedere al codice host fornito nel file .svc o per compilarlo.</span><span class="sxs-lookup"><span data-stu-id="67283-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67283-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67283-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="67283-103">Attributi</span><span class="sxs-lookup"><span data-stu-id="67283-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="67283-104">Servizio</span><span class="sxs-lookup"><span data-stu-id="67283-104">Service</span></span>  
 <span data-ttu-id="67283-105">Nome del tipo CLR del servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="67283-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="67283-106">Deve essere un nome completo di un tipo che implementa uno o più dei contatti del servizio.</span><span class="sxs-lookup"><span data-stu-id="67283-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="67283-107">Factory</span><span class="sxs-lookup"><span data-stu-id="67283-107">Factory</span></span>  
 <span data-ttu-id="67283-108">Nome del tipo CLR della factory dell'host del servizio usato per creare un'istanza dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="67283-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="67283-109">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="67283-109">This attribute is optional.</span></span> <span data-ttu-id="67283-110">Se non viene specificato, viene usata la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> predefinita, che restituisce un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="67283-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="67283-111">Debug</span><span class="sxs-lookup"><span data-stu-id="67283-111">Debug</span></span>  
 <span data-ttu-id="67283-112">Indica se il servizio Windows Communication Foundation (WCF) deve essere compilato con simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="67283-112">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="67283-113">`true` se il servizio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] deve essere compilato con simboli di debug; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="67283-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="67283-114">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="67283-114">Language</span></span>  
 <span data-ttu-id="67283-115">Specifica il linguaggio usato per la compilazione di tutto il codice inline contenuto nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="67283-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="67283-116">I valori possono rappresentare qualsiasi linguaggio supportato da .NET, inclusi C#, VB e JS, che fanno riferimento, rispettivamente, a C#, Visual Basic .NET e JScript .NET.</span><span class="sxs-lookup"><span data-stu-id="67283-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="67283-117">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="67283-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="67283-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="67283-118">CodeBehind</span></span>  
 <span data-ttu-id="67283-119">Specifica il file di origine per l'implementazione del servizio Web XML, quando la classe di implementazione non si trova nello stesso file e non è stata compilata in un assembly e inserita nella directory \Bin.</span><span class="sxs-lookup"><span data-stu-id="67283-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67283-120">Note</span><span class="sxs-lookup"><span data-stu-id="67283-120">Remarks</span></span>  
 <span data-ttu-id="67283-121">Il <xref:System.ServiceModel.ServiceHost> utilizzato per ospitare il servizio è un punto di estensibilità all'interno del modello di programmazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="67283-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="67283-122">Poiché un modello di factory può essere un tipo polimorfico di cui l'ambiente host non deve creare un'istanza direttamente, tale modello viene usato per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="67283-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="67283-123">L'implementazione predefinita usa la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="67283-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="67283-124">È però possibile fornire una propria factory (uno che restituisca l'host derivato) specificando il nome del tipo CLR dell'implementazione di factory nel [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva.</span><span class="sxs-lookup"><span data-stu-id="67283-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="67283-125">Per utilizzare è factory host del servizio personalizzato personalizzati anziché la factory predefinita, solo specificare il nome del tipo nel [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="67283-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="67283-126">È consigliabile garantire che le implementazioni presentino la massima semplicità possibile.</span><span class="sxs-lookup"><span data-stu-id="67283-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="67283-127">Se si usa un'elevata quantità di logica personalizzata, quest'ultima è più riutilizzabile se inserita nell'host anziché nella factory.</span><span class="sxs-lookup"><span data-stu-id="67283-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="67283-128">Ad esempio, per abilitare un endpoint compatibile con AJAX per `MyService`, specificare il <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> per il valore del `Factory` attributo, anziché il valore predefinito <xref:System.ServiceModel.Activation.ServiceHostFactory>nella [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva come Nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="67283-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67283-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="67283-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="67283-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67283-130">See Also</span></span>  
 [<span data-ttu-id="67283-131">Host di servizi personalizzati</span><span class="sxs-lookup"><span data-stu-id="67283-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
