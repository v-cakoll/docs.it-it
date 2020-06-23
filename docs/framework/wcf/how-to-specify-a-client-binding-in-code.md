---
title: "Procedura: specificare un'associazione al client in codice"
description: Informazioni su come specificare l'associazione per un client WCF in modo imperativo nel codice. Il client accede a un servizio in questo esempio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: e5e1dff98121985a598579d83043de838e21e5f1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244504"
---
# <a name="how-to-specify-a-client-binding-in-code"></a>Procedura: specificare un'associazione al client in codice
Questo esempio illustra un client creato in modo da utilizzare un servizio di calcolatrice. Inoltre, l'associazione a tale client viene specificata in modo imperativo in codice. Il client accede al servizio `CalculatorService` che implementa l'interfaccia `ICalculator`. Sia il servizio sia il client utilizzano la classe <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Questa procedura presuppone che il servizio di calcolatrice sia in esecuzione. Per informazioni sulla compilazione del servizio, vedere [procedura: specificare un'associazione al servizio nella configurazione](how-to-specify-a-service-binding-in-configuration.md). USA inoltre lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) fornisce per generare automaticamente i componenti client. Lo strumento genera il codice client di accesso al servizio.  
  
 Il client viene compilato in due parti. Lo strumento Svcutil.exe genera la classe `ClientCalculator` che implementa l'interfaccia `ICalculator`. Questa applicazione client viene quindi costruita creando un'istanza della classe `ClientCalculator` e specificando in codice l'associazione e l'indirizzo del servizio.  
  
 Per la copia di origine di questo esempio, vedere l'esempio di [base](./samples/basicbinding.md) .  
  
### <a name="to-specify-a-custom-binding-in-code"></a>Per specificare in codice un'associazione personalizzata  
  
1. Utilizzare Svcutil.exe dalla riga di comando per generare il codice da metadati del servizio.  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. Il client generato contiene l'interfaccia `ICalculator` che definisce il contratto di servizio che l'implementazione del client deve soddisfare.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. Il client generato contiene inoltre l'implementazione della classe `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. Creare un'istanza della classe `ClientCalculator` che utilizza la classe <xref:System.ServiceModel.BasicHttpBinding> in un'applicazione client e quindi chiamare le operazioni del servizio all'indirizzo specificato.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. Compilare ed eseguire il client.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
