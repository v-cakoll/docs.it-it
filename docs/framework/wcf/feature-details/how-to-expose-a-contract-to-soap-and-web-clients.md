---
title: 'Procedura: esporre un contratto a client SOAP e Web'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: fa02260976c710401a05cce3d723cc0f66804c6e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593132"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a>Procedura: esporre un contratto a client SOAP e Web

Per impostazione predefinita, Windows Communication Foundation (WCF) rende gli endpoint disponibili solo per i client SOAP. In [procedura: creare un servizio HTTP Web WCF di base](how-to-create-a-basic-wcf-web-http-service.md), un endpoint viene reso disponibile per i client non SOAP. Possono verificarsi casi in cui si desidera rendere lo stesso contratto disponibile in entrambi i modi, come endpoint Web e come endpoint SOAP. In questo argomento viene illustrato un esempio di come ottenere tale risultato.

## <a name="to-define-the-service-contract"></a>Per definire il contratto di servizio

1. Definire un contratto di servizio usando un'interfaccia contrassegnata con gli <xref:System.ServiceModel.ServiceContractAttribute> <xref:System.ServiceModel.Web.WebInvokeAttribute> <xref:System.ServiceModel.Web.WebGetAttribute> attributi e, come illustrato nel codice seguente:

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > Per impostazione predefinita, <xref:System.ServiceModel.Web.WebInvokeAttribute> esegue il mapping delle chiamate POST all'operazione. Tuttavia, è possibile definire il metodo di mapping all'operazione specificando un parametro "method=". <xref:System.ServiceModel.Web.WebGetAttribute> non dispone di un parametro "method=" ed esegue solo il mapping delle chiamate GET all'operazione del servizio.

2. Implementare il contratto di servizio, come illustrato nel codice seguente:

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a>Per ospitare il servizio

1. Creare un <xref:System.ServiceModel.ServiceHost> oggetto, come illustrato nel codice seguente:

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. Aggiungere un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.BasicHttpBinding> per l'endpoint SOAP, come illustrato nel codice seguente:

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. Aggiungere un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.WebHttpBinding> per l'endpoint non SOAP e aggiungere all' <xref:System.ServiceModel.Description.WebHttpBehavior> endpoint, come illustrato nel codice seguente:

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. Chiamare `Open()` su un' <xref:System.ServiceModel.ServiceHost> istanza di per aprire l'host del servizio, come illustrato nel codice seguente:

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a>Per chiamare operazioni del servizio mappate a GET in Internet Explorer

1. Aprire Internet Explorer e digitare " `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` " e premere INVIO. L'URL contiene l'indirizzo di base del servizio ( `http://localhost:8000/` ), l'indirizzo relativo dell'endpoint (""), l'operazione del servizio da chiamare ("EchoWithGet") e un punto interrogativo seguito da un elenco di parametri denominati separati da una e commerciale (&).

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a>Per chiamare operazioni del servizio sull'endpoint Web nel codice

1. Creare un'istanza di <xref:System.ServiceModel.Web.WebChannelFactory%601> all'interno di un blocco `using`, come mostrato nel codice seguente.

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> `Close()` viene automaticamente chiamato sul canale alla fine del blocco `using`.

1. Creare il canale e chiamare il servizio, come mostrato nel codice seguente.

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a>Per chiamare operazioni del servizio sull'endpoint SOAP

1. Creare un'istanza di <xref:System.ServiceModel.ChannelFactory> all'interno di un blocco `using`, come mostrato nel codice seguente.

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. Creare il canale e chiamare il servizio, come mostrato nel codice seguente.

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a>Per chiudere l'host del servizio

1. Chiudere l'host del servizio, come mostrato nel codice seguente.

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a>Esempio

Di seguito è riportato il listato di codice completo per questo argomento:

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a>Compilazione del codice

 Durante la compilazione di Service.cs fare riferimento a System.ServiceModel.dll e System.ServiceModel.Web.dll.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Modello di programmazione HTTP Web WCF](wcf-web-http-programming-model.md)
