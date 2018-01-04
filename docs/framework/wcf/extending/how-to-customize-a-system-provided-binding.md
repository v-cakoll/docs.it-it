---
title: 'Procedura: personalizzare un''associazione fornita dal sistema'
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
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9b048b5c57d174ac921793ee8677622b88a0595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="ddbef-102">Procedura: personalizzare un'associazione fornita dal sistema</span><span class="sxs-lookup"><span data-stu-id="ddbef-102">How to: Customize a System-Provided Binding</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ddbef-103"> include diverse associazioni fornite dal sistema che consentono di configurare alcune delle proprietà degli elementi di associazione sottostanti.</span><span class="sxs-lookup"><span data-stu-id="ddbef-103"> includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="ddbef-104">In questo argomento viene illustrato come impostare proprietà sugli elementi di associazione per creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ddbef-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ddbef-105">come creare direttamente e configurare gli elementi di associazione senza utilizzare le associazioni fornite dal sistema, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ddbef-105"> how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ddbef-106">creazione e l'estensione delle associazioni personalizzate, vedere [estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ddbef-106"> creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="ddbef-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tutte le associazioni sono costituite da *gli elementi di associazione*.</span><span class="sxs-lookup"><span data-stu-id="ddbef-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="ddbef-108">Ogni elemento di associazione deriva dalla classe <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ddbef-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="ddbef-109">Le associazioni fornite dal sistema, ad esempio <xref:System.ServiceModel.BasicHttpBinding>, creano e configurano propri elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="ddbef-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="ddbef-110">In questo argomento viene illustrato come accedere e modificare le proprietà di questi elementi di associazione che non sono direttamente esposte sull'associazione; in particolare, la classe <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="ddbef-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="ddbef-111">I singoli elementi di associazione sono inclusi in una raccolta rappresentata dalla classe <xref:System.ServiceModel.Channels.BindingElementCollection> e vengono aggiunti nell'ordine seguente: Flusso delle transazioni, Sessione affidabile, Protezione, Duplex composito, Unidirezionale, Protezione di flusso, Codifica messaggi e Trasporto.</span><span class="sxs-lookup"><span data-stu-id="ddbef-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="ddbef-112">Si noti che non tutti gli elementi di associazione elencati sono necessari in ogni associazione.</span><span class="sxs-lookup"><span data-stu-id="ddbef-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="ddbef-113">In questa raccolta di elementi di associazione possono essere inclusi anche elementi di associazione definiti dall'utente, che devono essere visualizzati nello stesso ordine descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ddbef-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="ddbef-114">Ad esempio, un trasporto definito dall'utente deve essere l'ultimo elemento della raccolta di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="ddbef-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="ddbef-115">La classe <xref:System.ServiceModel.BasicHttpBinding> contiene tre elementi di associazione:</span><span class="sxs-lookup"><span data-stu-id="ddbef-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="ddbef-116">Un elemento di associazione di sicurezza facoltativo: la classe <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> usata con il trasporto HTTP (protezione a livello di messaggio) o la classe <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> usata quando il livello di trasporto fornisce la protezione, caso in cui viene usato il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ddbef-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="ddbef-117">Un elemento di associazione del codificatore dei messaggi obbligatorio: <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> o <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ddbef-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="ddbef-118">Un elemento di associazione del trasporto obbligatorio: <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ddbef-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="ddbef-119">In questo esempio viene creata un'istanza dell'associazione, generare un *associazione personalizzata* , esaminare gli elementi di associazione nell'associazione personalizzata e, quando viene trovato l'elemento di associazione HTTP, viene impostata la `KeepAliveEnabled` proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="ddbef-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="ddbef-120">La proprietà `KeepAliveEnabled` non è esposta direttamente su `BasicHttpBinding`, pertanto è necessario creare un'associazione personalizzata per spostarsi verso il basso sull'elemento di associazione e impostare questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ddbef-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="ddbef-121">Per modificare un'associazione fornita dal sistema</span><span class="sxs-lookup"><span data-stu-id="ddbef-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="ddbef-122">Creare un'istanza della classe <xref:System.ServiceModel.BasicHttpBinding> e impostarne la modalità di sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="ddbef-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="ddbef-123">Creare un'associazione personalizzata dall'associazione e creare una classe <xref:System.ServiceModel.Channels.BindingElementCollection> da una delle proprietà dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ddbef-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="ddbef-124">Eseguire un ciclo nella classe <xref:System.ServiceModel.Channels.BindingElementCollection> e, quando viene trovata la classe <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, impostarne la proprietà <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="ddbef-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ddbef-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddbef-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ddbef-126">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ddbef-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
