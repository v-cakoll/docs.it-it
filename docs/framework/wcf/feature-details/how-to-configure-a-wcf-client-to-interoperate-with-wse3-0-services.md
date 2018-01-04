---
title: 'Procedura: configurare un client WCF per interagire con i servizi WSE 3.0'
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
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 214e0de13ba362bf4f101a665e943a424c56363c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="3a84e-102">Procedura: configurare un client WCF per interagire con i servizi WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3a84e-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="3a84e-103">I client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono compatibili a livello di transito con Web Services Enhancements 3.0 per servizi Microsoft .NET (WSE) quando i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono configurati per utilizzare la versione dell'agosto 2004 di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="3a84e-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="3a84e-104">Per configurare un client WCF che interagisca con il servizio Web WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3a84e-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="3a84e-105">Eseguire il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client per il servizio Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3a84e-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="3a84e-106">Per un Servizio Web WSE viene creata una classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a84e-106">For a WSE Web service, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class is created.</span></span>  
  
     <span data-ttu-id="3a84e-107">Per informazioni dettagliate sulla creazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, vedere il [procedura: creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="3a84e-107">For details about creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="3a84e-108">Creare una classe che rappresenta un'associazione che può comunicare con i servizi Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3a84e-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="3a84e-109">La classe seguente fa parte di [interagisce con WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) esempio.</span><span class="sxs-lookup"><span data-stu-id="3a84e-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="3a84e-110">Creare una classe che derivi dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="3a84e-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="3a84e-111">Nell'esempio di codice seguente viene creata una classe denominata `WseHttpBinding` che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="3a84e-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="3a84e-112">Aggiungere alla classe le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3a84e-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="3a84e-113">L'esempio di codice seguente definisce `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione del messaggio, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="3a84e-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="3a84e-114">Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3a84e-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="3a84e-115">Nell'esempio di codice seguente vengono specificati il trasporto, la codifica messaggi e le impostazioni della protezione dei messaggi ottenendo i valori delle proprietà `SecurityAssertion` e `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="3a84e-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="3a84e-116">Nel codice dell'applicazione client, aggiungere il codice per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3a84e-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="3a84e-117">Nell'esempio di codice seguente viene specificato che il client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve utilizzare la protezione e l'autenticazione messaggi come definito dall'asserzione di sicurezza turnkey WSE 3.0 `AnonymousForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="3a84e-117">The following code example specifies that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="3a84e-118">Sono inoltre necessarie sessioni protette e chiavi derivate.</span><span class="sxs-lookup"><span data-stu-id="3a84e-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="3a84e-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a84e-119">Example</span></span>  
 <span data-ttu-id="3a84e-120">Nell'esempio di codice seguente viene definita un'associazione personalizzata che espone proprietà che corrispondono alle proprietà di una asserzione di sicurezza turnkey WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3a84e-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="3a84e-121">L'associazione personalizzata, denominata `WseHttpBinding` viene quindi utilizzata per specificare le proprietà dell'associazione per un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a84e-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="3a84e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a84e-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="3a84e-123">Interoperabilità con WSE</span><span class="sxs-lookup"><span data-stu-id="3a84e-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
