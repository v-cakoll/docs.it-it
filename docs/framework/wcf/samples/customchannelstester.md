---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: eebe4f15095c7cefbd32971fd2f3ee308e9916b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` è uno strumento che può essere usato per testare le implementazioni del canale personalizzato in un set di contratti di servizio predefiniti. È possibile selezionare il set di contratti di servizio e passarlo allo strumento usando un file XML. Lo strumento genera quindi il servizio e il client che esercitano le implementazioni del canale personalizzate durante lo scambio di messaggi.  
  
### <a name="to-build-the-tool"></a>Per compilare lo strumento  
  
1.  Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  La compilazione della soluzione genera tre file: CustomChannelsTester.exe, TestSpec.xml e SampleRun.cmd. Il file SampleRun.cmd contiene una riga di comando di esempio in cui viene illustrato come utilizzare questo strumento per verificare il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.  
  
### <a name="to-run-the-tool"></a>Per eseguire lo strumento  
  
-   Al prompt dei comandi digitare il comando seguente:  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     L'utilizzo dell'opzione `/binding` è obbligatorio.  
  
     `/dll` è necessaria se il "associazione" non è un'associazione fornita dal sistema fornita da Windows Communication Foundation (WCF).  
  
     `/testspec` è facoltativo.  
  
     Crea server e client basati sulle specifiche del test e sull'associazione.  
  
     Esegue il client e il server e restituisce i risultati.  
  
     Di seguito è riportato l'esempio XML della descrizione delle specifiche del test (testspec.xml):  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
  
## <a name="see-also"></a>Vedere anche
