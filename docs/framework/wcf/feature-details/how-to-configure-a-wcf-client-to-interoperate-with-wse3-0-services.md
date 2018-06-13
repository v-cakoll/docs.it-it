---
title: 'Procedura: configurare un client WCF per interagire con i servizi WSE 3.0'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: e30403f9c97f31e93c22a9658ffb74d4d02a49ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490643"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="9ba19-102">Procedura: configurare un client WCF per interagire con i servizi WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="9ba19-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="9ba19-103">I client Windows Communication Foundation (WCF) sono compatibili a livello di transito con Web Services Enhancements 3.0 per i servizi Microsoft .NET (WSE) quando i client WCF vengono configurati per usare la versione di agosto 2004 della specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="9ba19-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="9ba19-104">Per configurare un client WCF che interagisca con il servizio Web WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="9ba19-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="9ba19-105">Eseguire la [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un client WCF per il servizio Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="9ba19-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="9ba19-106">Per un servizio Web WSE, viene creata una classe client WCF.</span><span class="sxs-lookup"><span data-stu-id="9ba19-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="9ba19-107">Per informazioni dettagliate sulla creazione di un client WCF, vedere la [procedura: creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="9ba19-108">Creare una classe che rappresenta un'associazione che può comunicare con i servizi Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="9ba19-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="9ba19-109">La classe seguente fa parte di [interagisce con WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) esempio.</span><span class="sxs-lookup"><span data-stu-id="9ba19-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="9ba19-110">Creare una classe che derivi dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="9ba19-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="9ba19-111">Nell'esempio di codice seguente viene creata una classe denominata `WseHttpBinding` che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="9ba19-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="9ba19-112">Aggiungere alla classe le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9ba19-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="9ba19-113">L'esempio di codice seguente definisce `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione del messaggio, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="9ba19-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="9ba19-114">Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="9ba19-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="9ba19-115">Nell'esempio di codice seguente vengono specificati il trasporto, la codifica messaggi e le impostazioni della protezione dei messaggi ottenendo i valori delle proprietà `SecurityAssertion` e `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="9ba19-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="9ba19-116">Nel codice dell'applicazione client, aggiungere il codice per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="9ba19-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="9ba19-117">Esempio di codice seguente specifica che il client WCF deve utilizzare la protezione del messaggio e l'autenticazione di base a quanto definito da WSE 3.0 `AnonymousForCertificate` asserzione di sicurezza turnkey.</span><span class="sxs-lookup"><span data-stu-id="9ba19-117">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="9ba19-118">Sono inoltre necessarie sessioni protette e chiavi derivate.</span><span class="sxs-lookup"><span data-stu-id="9ba19-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="9ba19-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ba19-119">Example</span></span>  
 <span data-ttu-id="9ba19-120">Nell'esempio di codice seguente viene definita un'associazione personalizzata che espone proprietà che corrispondono alle proprietà di una asserzione di sicurezza turnkey WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="9ba19-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="9ba19-121">L'associazione personalizzata, denominata `WseHttpBinding`, viene quindi utilizzato per specificare le proprietà di binding per un client WCF.</span><span class="sxs-lookup"><span data-stu-id="9ba19-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="9ba19-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ba19-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="9ba19-123">Interoperabilità con WSE</span><span class="sxs-lookup"><span data-stu-id="9ba19-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
