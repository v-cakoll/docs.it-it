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
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>Procedura: configurare un client WCF per interagire con i servizi WSE 3.0
I client Windows Communication Foundation (WCF) sono compatibili a livello di rete con i miglioramenti dei servizi Web 3,0 per i servizi di Microsoft .NET (WSE) quando i client WCF sono configurati per l'utilizzo della versione agosto 2004 della specifica WS-Addressing.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>Per configurare un client WCF che interagisca con il servizio Web WSE 3.0  
  
1. Eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un client WCF per il servizio Web WSE 3,0.  
  
     Per un servizio Web WSE, viene creata una classe client WCF.  
  
     Per informazioni dettagliate sulla creazione di un client WCF, vedere [procedura: creare un client](../how-to-create-a-wcf-client.md).  
  
2. Creare una classe che rappresenta un'associazione che può comunicare con i servizi Web WSE 3.0.  
  
     La classe seguente fa parte dell'esempio di [interoperabilità con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) .  
  
    1. Creare una classe che derivi dalla classe <xref:System.ServiceModel.Channels.Binding>.  
  
         Nell'esempio di codice seguente viene creata una classe denominata `WseHttpBinding` che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Aggiungere alla classe le proprietà che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione dei messaggi.  
  
         Nell'esempio di codice seguente vengono definite le `SecurityAssertion` proprietà,, `RequireDerivedKeys` `EstablishSecurityContext` e `MessageProtectionOrder` . Specificano l'asserzione di WSE chiavi in mano, se sono necessarie chiavi derivate, se vengono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione del messaggio, rispettivamente.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> per impostare le proprietà dell'associazione.  
  
         Nell'esempio di codice seguente vengono specificati il trasporto, la codifica messaggi e le impostazioni della protezione dei messaggi ottenendo i valori delle proprietà `SecurityAssertion` e `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. Nel codice dell'applicazione client, aggiungere il codice per impostare le proprietà dell'associazione.  
  
     Nell'esempio di codice riportato di seguito viene specificato che il client WCF deve utilizzare la protezione dei messaggi e l'autenticazione come definito dall' `AnonymousForCertificate` asserzione di sicurezza chiavi in mano di WSE 3,0. Sono inoltre necessarie sessioni protette e chiavi derivate.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita un'associazione personalizzata che espone proprietà che corrispondono alle proprietà di una asserzione di sicurezza turnkey WSE 3.0. L'associazione personalizzata, denominata `WseHttpBinding` , viene quindi utilizzata per specificare le proprietà di binding per un client WCF.  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.Binding>
- [Interoperabilità con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
