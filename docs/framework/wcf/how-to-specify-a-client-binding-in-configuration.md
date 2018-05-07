---
title: "Procedura: specificare un'associazione client nella configurazione"
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e2ea5a4b1c2ca9b661be5d4c653a3b5668bd26f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a>Procedura: specificare un'associazione client nella configurazione
In questo esempio, viene creata un'applicazione console client per utilizzare un servizio calcolatrice e nella configurazione viene spiegata in modo dichiarativo l'associazione per quel client. Il client accede al servizio `CalculatorService` che implementa l'interfaccia `ICalculator`. Sia il servizio sia il client utilizzano la classe <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Nella procedura illustrata si presuppone che il servizio calcolatrice sia in esecuzione. Per informazioni su come compilare il servizio, vedere [procedura: specificare un'associazione al servizio nella configurazione](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md). Viene inoltre utilizzata la [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) forniti per generare automaticamente i componenti client di Windows Communication Foundation (WCF). Lo strumento genera il codice e la configurazione client per l'accesso al servizio.  
  
 Il client viene compilato in due parti. Lo strumento Svcutil.exe genera la classe `ClientCalculator` che implementa l'interfaccia `ICalculator`. Questa applicazione client viene quindi costruita creando un'istanza di `ClientCalculator`.  
  
 La procedura solitamente consigliata consiste nello specificare in modo dichiarativo l'associazione e le informazioni dell'indirizzo nella configurazione anziché in modo imperativo nel codice. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. Più in generale, se le informazioni su associazione e indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.  
  
 È possibile eseguire tutti i seguenti passaggi di configurazione utilizzando il [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Per la copia di origine di questo esempio, vedere il [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) esempio.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>Specifica di un'associazione client nella configurazione  
  
1.  Utilizzare Svcutil.exe dalla riga di comando per generare il codice da metadati del servizio.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Il client generato contiene l'interfaccia `ICalculator` che definisce il contratto di servizio che l'implementazione del client deve soddisfare.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  Il client generato contiene inoltre l'implementazione della classe `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  Svcutil.exe genera inoltre la configurazione per il client che utilizza la classe <xref:System.ServiceModel.BasicHttpBinding>. Quando si utilizza Visual Studio, come nome del file app. config. Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate nell'implementazione del servizio. Non è necessario, inoltre, scrivere codice per recuperarle dal file di configurazione.  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]   
            
5.  Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  Compilare ed eseguire il client.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
