---
title: 'Procedura: configurare un client WCF per interagire con i servizi WSE 3.0'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 7dd50fcc07c6c090042cf87acb4aa5d2b5321a68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579579"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="3c441-102">Procedura: configurare un client WCF per interagire con i servizi WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3c441-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="3c441-103">I client Windows Communication Foundation (WCF) sono compatibili a livello di rete con i miglioramenti dei servizi Web 3,0 per i servizi di Microsoft .NET (WSE) quando i client WCF sono configurati per l'utilizzo della versione agosto 2004 della specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="3c441-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="3c441-104">Per configurare un client WCF che interagisca con il servizio Web WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3c441-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="3c441-105">Eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un client WCF per il servizio Web WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="3c441-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="3c441-106">Per un servizio Web WSE, viene creata una classe client WCF.</span><span class="sxs-lookup"><span data-stu-id="3c441-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="3c441-107">Per informazioni dettagliate sulla creazione di un client WCF, vedere [procedura: creare un client](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="3c441-107">For details about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="3c441-108">Creare una classe che rappresenta un'associazione che può comunicare con i servizi Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c441-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="3c441-109">La classe seguente fa parte dell'esempio di [interoperabilità con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) .</span><span class="sxs-lookup"><span data-stu-id="3c441-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1. <span data-ttu-id="3c441-110">Creare una classe che derivi dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="3c441-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="3c441-111">Nell'esempio di codice seguente viene creata una classe denominata `WseHttpBinding` che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="3c441-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="3c441-112">Aggiungere alla classe le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3c441-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="3c441-113">Nell'esempio di codice seguente vengono definite le `SecurityAssertion` proprietà,, `RequireDerivedKeys` `EstablishSecurityContext` e `MessageProtectionOrder` .</span><span class="sxs-lookup"><span data-stu-id="3c441-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="3c441-114">Specificano l'asserzione di WSE chiavi in mano, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione del messaggio, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="3c441-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="3c441-115">Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3c441-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="3c441-116">Nell'esempio di codice seguente vengono specificati il trasporto, la codifica messaggi e le impostazioni della protezione dei messaggi ottenendo i valori delle proprietà `SecurityAssertion` e `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="3c441-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="3c441-117">Nel codice dell'applicazione client, aggiungere il codice per impostare le proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3c441-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="3c441-118">Nell'esempio di codice riportato di seguito viene specificato che il client WCF deve utilizzare la protezione dei messaggi e l'autenticazione come definito dall' `AnonymousForCertificate` asserzione di sicurezza chiavi in mano di WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="3c441-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="3c441-119">Sono inoltre necessarie sessioni protette e chiavi derivate.</span><span class="sxs-lookup"><span data-stu-id="3c441-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="3c441-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c441-120">Example</span></span>  
 <span data-ttu-id="3c441-121">Nell'esempio di codice seguente viene definita un'associazione personalizzata che espone proprietà che corrispondono alle proprietà di una asserzione di sicurezza turnkey WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c441-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="3c441-122">L'associazione personalizzata, denominata `WseHttpBinding` , viene quindi utilizzata per specificare le proprietà di binding per un client WCF.</span><span class="sxs-lookup"><span data-stu-id="3c441-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="3c441-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c441-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="3c441-124">Interoperabilità con WSE</span><span class="sxs-lookup"><span data-stu-id="3c441-124">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
