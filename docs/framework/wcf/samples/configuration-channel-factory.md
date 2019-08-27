---
title: Configurazione di una channel factory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 1b74c15599ebc932a2a0ed46d646b54bec986794
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045649"
---
# <a name="configuration-channel-factory"></a>Configurazione di una channel factory
In questo esempio viene descritto l'utilizzo di <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. Consente <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> la gestione centralizzata della configurazione client WCF. Può essere anche utile in scenari nei quali la configurazione viene selezionata o modificata dopo la fase di caricamento del dominio dell'applicazione.

## <a name="demonstrates"></a>Dimostrazione
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Discussione
 In questo esempio viene descritto come utilizzare <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> per aggiungere uno specifico file di configurazione a un'applicazione client, senza che sia necessario utilizzare il file di configurazione dell'applicazione predefinito.

 L'esempio è costituito da due progetti. Il primo progetto è un servizio semplice in esecuzione per rispondere a messaggi provenienti dai client. Il secondo progetto è un'applicazione client che compila due oggetti <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizzando un <xref:System.Configuration.ExeConfigurationFileMap> per il file di configurazione Test.config e li utilizza per comunicare con il servizio. Entrambi i client comunicano con il servizio utilizzando la configurazione specificata in Test.config.

 Il codice seguente aggiunge un file di configurazione personalizzato a un'applicazione client.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Aprire Visual Studio 2012 con privilegi di amministratore.

2. Fare clic con il pulsante destro del mouse sulla soluzione ConfigurationChannelFactory (2 progetti), quindi scegliere **Proprietà**.

3. In **Proprietà comuni**selezionare **progetto di avvio**, quindi fare clic su **progetti di avvio multipli**.

4. Spostare il progetto di **servizio** all'inizio dell'elenco, con l' **azione ' Avvia '** , quindi spostare il progetto **client** dopo il progetto di **servizio** , anche con l' **azione ' Avvia '** , in modo che il progetto **client** venga eseguito dopo il progetto di **servizio** .

5. Fare clic su **OK**, quindi premere F5 (o CTRL + F5) per eseguire l'esempio.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
